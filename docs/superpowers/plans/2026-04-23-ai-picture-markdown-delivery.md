# AI Picture Markdown Delivery Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Produce a reusable Markdown showcase template, a filled example file, and a beginner-friendly GitHub upload guide for a first-time GitHub user sharing locally stored AI-generated images.

**Architecture:** Keep the deliverables document-first and low-friction. Create one reusable showcase template, one example-filled showcase page that demonstrates the folder and image path conventions, and one standalone GitHub guide that explains account setup, repository creation, Git installation, and the first `add`/`commit`/`push` flow in plain Chinese.

**Tech Stack:** Markdown, plain text documentation, local workspace files

---

### Task 1: Create the reusable showcase template

**Files:**
- Create: `C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Template.md`
- Check: `C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Template.md`

- [ ] **Step 1: Write the template file**

Create a Markdown file with these sections:

```md
# AI 图片提示词作品集

> 这里可以写一句话简介，例如：这个页面用来分享我使用不同提示词生成的 AI 图片作品。

## 内容说明

- 记录不同主题的提示词案例
- 展示生成结果图
- 持续更新

## 案例目录

- [案例 01：示例标题](#案例-01示例标题)

---

## 案例 01：示例标题

### 生成图片

![案例 01 图片 1](./images/case-01/image-01.png)

### 提示词

```text
把这里替换成你的提示词
```

### 使用模型

- GPT-4o Image / Midjourney / Stable Diffusion / 其他

### 简短说明

这里写这一组图片想表达的内容，或者你为什么喜欢这个结果。
```

- [ ] **Step 2: Verify the file structure is readable**

Run:

```powershell
Get-Content -Raw 'C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Template.md'
```

Expected: The file contains a complete Chinese template with title, directory, image, prompt, model, and note sections.

### Task 2: Create the filled example showcase

**Files:**
- Create: `C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Example.md`
- Check: `C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Example.md`

- [ ] **Step 1: Write the example file**

Create a Markdown example that demonstrates relative image paths and long-term structure:

```md
# AI 图片提示词作品集示例

> 这是一个示例页面，演示如何在 GitHub 中展示本地图片和提示词案例。

## 建议目录结构

```text
AIpicture/
├─ AI-Prompt-Showcase.md
└─ images/
   ├─ case-01/
   │  ├─ image-01.png
   │  └─ image-02.png
   └─ case-02/
      └─ image-01.png
```

## 案例 01：梦幻森林少女

### 生成图片

![梦幻森林少女 1](./images/case-01/image-01.png)
![梦幻森林少女 2](./images/case-01/image-02.png)

### 提示词

```text
一个站在薄雾森林里的少女，长发，白色裙子，阳光从树林缝隙洒下，电影感构图，细节丰富，梦幻氛围
```

### 使用模型

- GPT Image 1

### 简短说明

这一组主要想测试“梦幻感”和“森林光影”的表现，最后效果比较柔和，适合做氛围感主题。
```

- [ ] **Step 2: Verify the example reads like a real reference**

Run:

```powershell
Get-Content -Raw 'C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Example.md'
```

Expected: The file shows a realistic example with relative image paths under `./images/...`.

### Task 3: Write the beginner GitHub upload guide

**Files:**
- Create: `C:\Users\12822\Desktop\makemyself\AIpicture\GitHub-Push-Guide-For-Beginners.md`
- Check: `C:\Users\12822\Desktop\makemyself\AIpicture\GitHub-Push-Guide-For-Beginners.md`

- [ ] **Step 1: Write the guide**

Create a Chinese guide that covers:

```md
# GitHub 上传教程（新手版）

## 第 1 步：注册 GitHub
## 第 2 步：新建仓库
## 第 3 步：安装 Git
## 第 4 步：配置用户名和邮箱
## 第 5 步：整理本地文件
## 第 6 步：初始化仓库
## 第 7 步：连接远程仓库
## 第 8 步：执行 add / commit / push
## 第 9 步：检查 GitHub 页面
## 常见问题
```

The guide must explain `repository`, `commit`, and `push` in plain language and mention that `git` is not currently available in this environment, so Git must be installed before command execution.

- [ ] **Step 2: Verify the guide covers the complete first-push flow**

Run:

```powershell
Get-Content -Raw 'C:\Users\12822\Desktop\makemyself\AIpicture\GitHub-Push-Guide-For-Beginners.md'
```

Expected: The file explains the full first-time GitHub flow in Chinese, from account creation to checking the uploaded Markdown page.

### Task 4: Cross-check consistency and handoff

**Files:**
- Check: `C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Template.md`
- Check: `C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Example.md`
- Check: `C:\Users\12822\Desktop\makemyself\AIpicture\GitHub-Push-Guide-For-Beginners.md`

- [ ] **Step 1: Verify all three files use the same folder convention**

Run:

```powershell
Select-String -Path `
  'C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Template.md',`
  'C:\Users\12822\Desktop\makemyself\AIpicture\AI-Prompt-Showcase-Example.md',`
  'C:\Users\12822\Desktop\makemyself\AIpicture\GitHub-Push-Guide-For-Beginners.md' `
  -Pattern 'images/case-01|AI-Prompt-Showcase|git|push'
```

Expected: The output confirms the same file naming and folder structure are referenced consistently.

- [ ] **Step 2: Final review for beginner clarity**

Check these points manually:

```text
- Terms are explained in plain Chinese
- Commands are copyable
- Relative image paths are shown explicitly
- The current missing-Git constraint is called out
```

- [ ] **Step 3: Commit**

After Git is installed and configured, run:

```bash
git add AI-Prompt-Showcase-Template.md AI-Prompt-Showcase-Example.md GitHub-Push-Guide-For-Beginners.md docs/superpowers/plans/2026-04-23-ai-picture-markdown-delivery.md
git commit -m "docs: add AI picture showcase template and GitHub guide"
```
