<div align="center">

# 📄 Resume Tailor Skill

**Transform your master resume into a job-specific, ATS-optimized resume in minutes.**  
**将你的完整简历，一键裁剪为针对特定JD的定制版本。**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Works with Claude](https://img.shields.io/badge/Works%20with-Claude-blueviolet)](https://claude.ai)
[![Works with ChatGPT](https://img.shields.io/badge/Works%20with-ChatGPT-green)](https://chat.openai.com)
[![Works with DeepSeek](https://img.shields.io/badge/Works%20with-DeepSeek-blue)](https://chat.deepseek.com)
[![Works with Kimi](https://img.shields.io/badge/Works%20with-Kimi-orange)](https://kimi.moonshot.cn)

[English](#english) · [中文说明](#中文说明)

</div>

---

## English

### ✨ What It Does

This is a **prompt-based AI skill** that works with any major LLM. You provide:
1. Your **master resume** (the full one with all experiences)
2. A **job description (JD)**

The AI will tailor your resume by:
- Selecting the most JD-relevant experiences
- Rewriting bullets using **STAR format** (achievement-first: "Achieved X by doing Y")
- Aligning keywords to the JD for **ATS compatibility**
- Enforcing **precise formatting rules** (character limits per line, 1-page max)
- Outputting both **Markdown** and a formatted **.docx** file

**Supports English and Chinese (中文) output.**

---

### 🤖 Compatible Platforms

This skill works with **any LLM that supports a system prompt**. Just paste `SKILL.md` as your system prompt.

| Platform | How to Use | Notes |
|----------|-----------|-------|
| **Claude** (claude.ai) | Paste `SKILL.md` as system prompt, or use as a Claude Skill | Best docx generation |
| **ChatGPT** (GPT-4o) | Paste into Custom Instructions or system prompt | Works great |
| **DeepSeek** | Paste into system prompt | Free, strong Chinese support |
| **Kimi** (Moonshot) | Paste into system prompt | Excellent for Chinese resumes |
| **Gemini Advanced** | Paste into system instruction | Works well |
| **Coze** | Create a Bot, paste as System Prompt | Build a shareable product |
| **Dify** | Use as workflow system prompt | Self-hostable open source |

---

### 🚀 Quick Start

#### Option A — Claude.ai (Recommended)

1. Open [claude.ai](https://claude.ai) and start a new chat
2. Copy the entire contents of [`SKILL.md`](./SKILL.md)
3. Paste it as your **first message** prefixed with:
   > "Please follow these instructions for our entire conversation: [paste SKILL.md here]"
4. Upload your resume (`.docx` or `.pdf`) + paste your JD
5. Follow the prompts

#### Option B — ChatGPT

1. Go to [chat.openai.com](https://chat.openai.com) → click your profile → **Customize ChatGPT**
2. Paste [`SKILL.md`](./SKILL.md) contents into **"Custom Instructions"**
3. Start a new chat, upload resume + paste JD

#### Option C — DeepSeek / Kimi / Other

1. Open a new chat
2. Send this as your **first message**:
```
You are a resume tailoring assistant. Please follow these instructions exactly for this entire conversation:

[paste full contents of SKILL.md here]

Understood? Please confirm and wait for me to upload my resume and JD.
```
3. Upload resume + paste JD when ready

#### Option D — Coze (Build a Shareable Bot)

1. Go to [coze.com](https://www.coze.com) → **Create Bot**
2. Paste [`SKILL.md`](./SKILL.md) into the **System Prompt** field
3. Enable the **File Upload** plugin
4. Publish and share the link with anyone

#### Option E — Dify (Self-Hosted)

1. Deploy [Dify](https://github.com/langgenius/dify)
2. Create a new **Chatflow**
3. Paste [`SKILL.md`](./SKILL.md) as the system prompt node
4. Add a file upload variable for the resume input

---

### 💬 What the AI Will Ask You

After you provide your resume and JD, the AI will ask:

| Question | Options |
|----------|---------|
| Output language? | 🇺🇸 English / 🇨🇳 中文 |
| How many work experience entries? | 3 / 4 / 5 / All |
| Personal Summary section? | Yes / No |
| Project Experience section? | Yes / No (+ how many) |
| Bullets per entry? | 2 / 3 / Mixed |

---

### 📐 Formatting Specs

**English Resume**
| Setting | Value |
|---------|-------|
| Font | Arial 10pt |
| Margins | 0.5 inches |
| Max lines | 53 lines (1 page) |
| 1-line bullet | ≤ 112 characters |
| 2-line bullet | 214–220 characters |
| Non-bullet text (Summary, Skills) | ~130 chars/line |

**Chinese Resume 中文简历**
| 设置 | 规格 |
|------|------|
| 字体 | 宋体 10pt |
| 页边距 | 0.5英寸 |
| 最大行数 | 53行（1页） |
| 单行bullet | ≤ 50字 |
| 双行bullet | 90–96字 |
| 非bullet文字 | 每行~53字 |

---

### 📁 File Structure

```
resume-tailor/
├── SKILL.md                      # Main prompt — paste this into your AI
├── README.md                     # This file
└── references/
    ├── formatting-rules.md       # Full formatting spec (fonts, margins, char limits)
    ├── docx-template.md          # Node.js code template for .docx generation
    ├── verb-bank.md              # 80+ action verbs (English + Chinese)
    ├── example-output-en.md      # Sample English tailored resume
    └── example-output-zh.md      # Sample Chinese tailored resume
```

---

### 📝 Bullet Writing Philosophy

Every bullet follows this formula:

```
[Achievement/Result] + by/through + [Action + Context]
```

✅ `Grew enterprise ARR by 18% by launching a self-serve analytics dashboard adopted by 40+ accounts`  
✅ `将用户留存率提升18%，通过为企业客户设计个性化新手引导流程`  
❌ `Responsible for improving the deployment process`  
❌ `负责优化部署流程`

Numbers you don't have are written as `[X%]`, `[N users]` — you replace them with real data.

---


### 📄 License

MIT License — free to use, modify, and distribute.

---

---

## 中文说明

### ✨ 这是什么

这是一个**基于提示词的AI简历定制工具**，适配所有主流大模型。你只需提供：
1. 你的**完整简历**（包含所有经历的母版）
2. 目标职位的**JD（岗位描述）**

AI会帮你：
- 筛选与JD最相关的经历
- 用**STAR法则**重写每条bullet（成就开头："实现X，通过Y"）
- 对齐JD关键词，**ATS友好**
- 严格控制**排版格式**（字数限制、1页以内）
- 输出 **Markdown** 和格式化的 **.docx** 文件

**支持中文和英文输出。**

---

### 🤖 支持的平台

只要支持系统提示词（System Prompt）的AI都可以用，把 `SKILL.md` 的内容贴进去即可。

| 平台 | 使用方式 | 备注 |
|------|---------|------|
| **Claude** (claude.ai) | 贴入System Prompt 或作为Claude Skill使用 | docx生成最佳 |
| **ChatGPT** (GPT-4o) | 贴入Custom Instructions或对话开头 | 效果很好 |
| **DeepSeek** | 贴入系统提示词 | 免费，中文效果强 |
| **Kimi**（月之暗面） | 贴入系统提示词 | 中文理解优秀 |
| **Gemini Advanced** | 贴入System Instruction | 可用 |
| **Coze**（字节跳动） | 创建Bot，贴入System Prompt | 可做成可分享的产品 |
| **Dify** | 作为工作流系统提示词 | 开源可自部署 |

---

### 🚀 快速开始

#### 方式A — Claude.ai（推荐）

1. 打开 [claude.ai](https://claude.ai) 新建对话
2. 复制 [`SKILL.md`](./SKILL.md) 的全部内容
3. 作为第一条消息发送，前面加上：
   > "请在我们整个对话中严格遵循以下指令：[粘贴SKILL.md内容]"
4. 上传简历（`.docx` 或 `.pdf`）+ 粘贴JD
5. 按照AI的提示操作

#### 方式B — DeepSeek / Kimi（免费推荐）

1. 打开新对话
2. 发送以下内容作为第一条消息：
```
你是一个简历定制助手，请在整个对话中严格按照以下指令操作：

[粘贴SKILL.md全部内容]

明白了请确认，然后等我上传简历和JD。
```
3. 上传简历 + 粘贴JD

#### 方式C — Coze（做成可分享的Bot）

1. 进入 [coze.cn](https://www.coze.cn) → **创建Bot**
2. 将 [`SKILL.md`](./SKILL.md) 内容粘贴到**系统提示词**
3. 开启**文件上传**插件
4. 发布后把链接分享给任何人使用

---

### 💬 AI会问你哪些问题

提供简历和JD后，AI会依次询问：

| 问题 | 选项 |
|------|------|
| 输出语言？ | 🇨🇳 中文 / 🇺🇸 English |
| 想要几条工作经历？ | 3 / 4 / 5 / 全部 |
| 需要个人简介板块？ | 是 / 否 |
| 需要项目经历板块？ | 是 / 否（+ 几条） |
| 每条经历几个bullet？ | 2 / 3 / 混合 |

---

### 📄 开源协议

MIT License — 免费使用、修改和分发。
