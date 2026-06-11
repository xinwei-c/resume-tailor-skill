# DOCX Template for Resume Tailor

Ready-to-adapt Node.js template using the `docx` library.
Install: `npm install -g docx`

---

## Full Template (English)

```javascript
const {
  Document, Packer, Paragraph, TextRun, AlignmentType,
  BorderStyle, LevelFormat, WidthType, HeadingLevel
} = require('docx');
const fs = require('fs');

// ── CONFIG ──────────────────────────────────────────────
const LANG = 'en'; // 'en' or 'zh'
const FONT = LANG === 'zh' ? 'SimSun' : 'Arial';
const BODY_SIZE = 20;                             // 10pt for both EN and ZH (half-points)
const NAME_SIZE = 28;                             // 14pt for name (line 1) — both languages
const H2_SIZE  = 22;                              // 11pt section headings
const MARGIN   = 720;                             // 0.5 inches in DXA

// ── HELPERS ─────────────────────────────────────────────
const sectionHeading = (text) => new Paragraph({
  children: [new TextRun({ text, font: FONT, size: H2_SIZE, bold: true })],
  spacing: { before: 180, after: 60 },
  border: {
    bottom: { style: BorderStyle.SINGLE, size: 6, color: "2E75B6", space: 1 }
  }
});

// Line 1: Company | Location (bold, normal casing) ......... Dates (bold, right-aligned)
const jobHeader = (company, location, dates) => new Paragraph({
  spacing: { before: 100, after: 20 },
  tabStops: [{ type: "right", position: 10800 }],
  children: [
    new TextRun({ text: `${company} | ${location}`, font: FONT, size: BODY_SIZE, bold: true }),
    new TextRun({ text: `\t${dates}`, font: FONT, size: BODY_SIZE, bold: true }),
  ]
});

// Line 2: Job title — next line, regular weight, NOT italic
const entryTitle = (title) => new Paragraph({
  spacing: { before: 0, after: 30 },
  children: [new TextRun({ text: title, font: FONT, size: BODY_SIZE })]
});

const bullet = (text) => new Paragraph({
  numbering: { reference: "resume-bullets", level: 0 },
  children: [new TextRun({ text, font: FONT, size: BODY_SIZE })],
  spacing: { before: 30, after: 30 },
});

// ── DOCUMENT ────────────────────────────────────────────
const doc = new Document({
  numbering: {
    config: [{
      reference: "resume-bullets",
      levels: [{
        level: 0,
        format: LevelFormat.BULLET,
        text: "•",
        alignment: AlignmentType.LEFT,
        style: { paragraph: { indent: { left: 360, hanging: 180 } } }
      }]
    }]
  },
  styles: {
    default: {
      document: { run: { font: FONT, size: BODY_SIZE } }
    }
  },
  sections: [{
    properties: {
      page: {
        size: { width: 12240, height: 15840 }, // US Letter
        margin: { top: MARGIN, right: MARGIN, bottom: MARGIN, left: MARGIN }
      }
    },
    children: [

      // ── LINE 1: Name (14pt bold centered) ────────────────
      new Paragraph({
        alignment: AlignmentType.CENTER,
        spacing: { after: 40 },
        children: [new TextRun({ text: "FULL NAME", font: FONT, size: NAME_SIZE, bold: true })]
      }),
      // ── LINE 2: Contact info (10pt centered) ─────────────
      new Paragraph({
        alignment: AlignmentType.CENTER,
        spacing: { after: 80 },
        children: [new TextRun({
          text: "email@example.com  |  +1 (555) 000-0000  |  linkedin.com/in/handle  |  City, State",
          font: FONT, size: BODY_SIZE
        })]
      }),

      // ── SUMMARY ────────────────────────────────────────
      sectionHeading("Summary"),
      new Paragraph({
        children: [new TextRun({
          text: "2–3 sentence tailored summary here.",
          font: FONT, size: BODY_SIZE
        })],
        spacing: { before: 40, after: 40 }
      }),

      // ── EXPERIENCE ─────────────────────────────────────
      sectionHeading("Experience"),

      // Entry 1
      ...jobHeader("Senior Software Engineer", "Acme Corp", "Jan 2022 – Present"),
      bullet("Reduced deployment time by 40% by redesigning CI/CD pipeline with GitHub Actions"),
      bullet("Grew platform reliability to 99.9% uptime by leading incident response overhaul across [N] services"),
      bullet("Delivered [X] new API integrations by partnering with 3 product teams in a 6-week sprint"),

      // Entry 2
      ...jobHeader("Software Engineer", "Startup Inc", "Jun 2019 – Dec 2021"),
      bullet("Launched mobile app v2.0 reaching [X]k downloads by redesigning UX with data-driven A/B testing"),
      bullet("Optimized database query performance by [X]% by introducing indexing strategy across 12 tables"),
      bullet("Spearheaded migration from monolith to microservices, enabling independent scaling of [N] modules"),

      // ── SKILLS ─────────────────────────────────────────
      sectionHeading("Skills"),
      new Paragraph({
        children: [
          new TextRun({ text: "Technical: ", font: FONT, size: BODY_SIZE, bold: true }),
          new TextRun({ text: "Python, TypeScript, React, AWS, Docker, Kubernetes, PostgreSQL", font: FONT, size: BODY_SIZE }),
        ],
        spacing: { before: 40, after: 20 }
      }),
      new Paragraph({
        children: [
          new TextRun({ text: "Soft Skills: ", font: FONT, size: BODY_SIZE, bold: true }),
          new TextRun({ text: "Cross-functional collaboration, Agile/Scrum, Technical roadmapping", font: FONT, size: BODY_SIZE }),
        ],
        spacing: { before: 20, after: 40 }
      }),

      // ── EDUCATION ──────────────────────────────────────
      sectionHeading("Education"),
      ...jobHeader("B.S. Computer Science", "State University", "2015 – 2019"),
    ]
  }]
});

Packer.toBuffer(doc).then(buf => {
  fs.writeFileSync("tailored-resume.docx", buf);
  console.log("✅ tailored-resume.docx created");
});
```

---

## Chinese Variant Notes

Change the config block at the top:
```javascript
const LANG = 'zh';
// Results in: SimSun font, 10pt body, 16pt H1, 12pt H2
```

Chinese section headings use same `sectionHeading()` helper — no changes needed.

For Chinese bullets, the `•` bullet character and indent remain the same.

---

## Validation

After generating, always validate:
```bash
python scripts/office/validate.py tailored-resume.docx
```

If validation fails, unpack → fix XML → repack per the docx skill instructions.
