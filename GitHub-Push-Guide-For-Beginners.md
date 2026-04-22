# GitHub 上传教程（新手版）

> 这份教程是给第一次使用 GitHub 的人准备的。你不需要提前会 Git，我会把每一步都尽量写清楚。

## 先认识 3 个最常见的词

### 1. 仓库

仓库就是你在 GitHub 上存放项目文件的地方。你可以把它理解成一个在线项目文件夹。

### 2. commit

`commit` 可以理解成一次“保存记录”。

它不是普通保存，而是告诉 Git：

“我现在把这一批修改正式记下来。”

### 3. push

`push` 可以理解成“把本地电脑上的内容上传到 GitHub”。

也就是把你本地已经记录好的内容，真正发送到 GitHub 网站上。

---

## 你这次要完成的目标

你最终要做到的是：

1. 在 GitHub 上创建一个仓库
2. 把你的 Markdown 文件和图片放进本地项目文件夹
3. 用 Git 把这些内容上传到 GitHub
4. 打开 GitHub 页面，确认 Markdown 和图片都显示正常

---

## 第 1 步：注册 GitHub 账号

1. 打开 [GitHub 官网](https://github.com/)
2. 点击右上角的 `Sign up`
3. 按页面提示输入：
- 邮箱
- 密码
- 用户名
4. 完成验证
5. 注册成功后登录 GitHub

如果你已经有账号，这一步可以跳过。

---

## 第 2 步：新建一个仓库

登录 GitHub 后：

1. 点击右上角头像旁边的 `+`
2. 选择 `New repository`
3. 填写仓库信息：
- Repository name：建议填 `AIpicture` 或你想要的名字
- Description：可以写 `My AI image prompt showcase`
4. 选择仓库公开方式：
- `Public`：任何人都能看到，适合展示作品
- `Private`：只有你自己和你授权的人能看到
5. 点击 `Create repository`

建议你第一次先选 `Public`，这样更方便展示。

---

## 第 3 步：在 Windows 上安装 Git

你当前这个环境里，`git` 命令还不能用，所以这一步是必须的。

### 安装方法

1. 打开 [Git for Windows 官网](https://git-scm.com/download/win)
2. 下载 Windows 安装包
3. 双击安装
4. 安装过程中大部分选项保持默认即可
5. 安装完成后，关闭你现在打开的终端，再重新打开

### 怎么确认安装成功

打开 PowerShell，输入：

```powershell
git --version
```

如果你看到类似这样的输出，就说明安装成功了：

```text
git version 2.xx.x.windows.x
```

如果还是提示找不到 `git`，通常是因为：

- 安装后终端没有重开
- Git 没有正确加入 PATH

这时最简单的方法是重启 PowerShell 或重启电脑后再试一次。

---

## 第 4 步：配置 Git 用户名和邮箱

安装好 Git 后，先告诉 Git 你是谁。

在 PowerShell 里输入：

```powershell
git config --global user.name "你的 GitHub 用户名"
git config --global user.email "你的 GitHub 注册邮箱"
```

例如：

```powershell
git config --global user.name "yourname"
git config --global user.email "yourname@example.com"
```

然后可以检查一下：

```powershell
git config --global --list
```

如果你能看到 `user.name` 和 `user.email`，就说明配置好了。

---

## 第 5 步：整理你的本地文件

先把你要上传的内容整理到一个文件夹里。

建议结构像这样：

```text
AIpicture/
├─ AI-Prompt-Showcase.md
└─ images/
   ├─ case-01/
   │  ├─ image-01.png
   │  └─ image-02.png
   ├─ case-02/
   │  └─ image-01.png
   └─ case-03/
      └─ image-01.png
```

### 你需要做的事情

1. 把你的 Markdown 文件放进根目录
2. 新建一个 `images` 文件夹
3. 每一组图片单独建一个文件夹，例如：
- `images/case-01/`
- `images/case-02/`
4. 把对应图片放进去

### 最重要的一点

Markdown 里的图片路径要和真实文件位置对应。

例如你写：

```md
![案例图](./images/case-01/image-01.png)
```

那你的图片就必须真的在：

```text
images/case-01/image-01.png
```

---

## 第 6 步：进入项目文件夹

打开 PowerShell，然后进入你的项目文件夹。

例如你的文件夹在桌面：

```powershell
cd C:\Users\12822\Desktop\makemyself\AIpicture
```

如果你的实际路径不一样，就换成你自己的路径。

你可以用这个命令确认自己进对了目录：

```powershell
Get-Location
```

---

## 第 7 步：初始化 Git 仓库

第一次上传时，要先把这个文件夹变成 Git 仓库。

在 PowerShell 里输入：

```powershell
git init
```

执行后，这个文件夹就开始被 Git 管理了。

你可以再输入：

```powershell
git status
```

如果看到类似 “No commits yet” 或者列出未跟踪文件，说明初始化成功。

---

## 第 8 步：把本地仓库连接到 GitHub 仓库

你在 GitHub 上创建完仓库后，会有一个仓库地址。

它通常长这样：

```text
https://github.com/你的用户名/AIpicture.git
```

把它复制下来，然后在 PowerShell 里输入：

```powershell
git remote add origin https://github.com/你的用户名/AIpicture.git
```

例如：

```powershell
git remote add origin https://github.com/yourname/AIpicture.git
```

你可以检查是否添加成功：

```powershell
git remote -v
```

如果看到 `origin` 对应你的 GitHub 地址，就说明成功了。

---

## 第 9 步：把文件加入 Git

现在开始准备第一次上传。

先执行：

```powershell
git add .
```

这一步的意思是：

把当前文件夹里所有改动都加入这次准备上传的内容里。

然后执行：

```powershell
git status
```

如果你看到很多文件显示为 `new file`，说明已经加进去了。

---

## 第 10 步：创建第一次 commit

执行：

```powershell
git commit -m "first upload"
```

这一步的意思是：

把你刚刚加入的那些文件，正式保存成一次记录。

如果 commit 成功，你会看到类似：

```text
[main (root-commit) xxxxxxx] first upload
```

---

## 第 11 步：把内容 push 到 GitHub

第一次 push 时，建议这样执行：

```powershell
git branch -M main
git push -u origin main
```

这两条命令分别表示：

- `git branch -M main`
把当前分支名字统一改成 `main`

- `git push -u origin main`
把本地 `main` 分支上传到 GitHub，并建立默认关联

### 如果 GitHub 让你登录

这是正常的。

你可能会遇到以下情况：

- 浏览器弹出 GitHub 登录
- 让你确认授权
- 要求输入用户名和令牌

现在 GitHub 一般不再直接用密码做命令行验证，所以如果提示认证，通常按 GitHub 提示完成网页登录授权就可以。

---

## 第 12 步：检查 GitHub 页面

push 成功后：

1. 打开你的 GitHub 仓库页面
2. 刷新页面
3. 看看这些文件是否已经出现：
- Markdown 文件
- `images` 文件夹
- 你的图片文件

然后点击你的 Markdown 文件，检查：

1. 标题有没有正常显示
2. 图片有没有正常显示
3. 提示词排版是否正常

---

## 如果图片没有显示怎么办

优先检查下面这几个问题：

### 1. 图片路径写错了

例如 Markdown 写的是：

```md
![图](./images/case-01/image-01.png)
```

那实际文件也必须是：

```text
images/case-01/image-01.png
```

### 2. 图片没有一起上传

你可能只上传了 `.md` 文件，没有把 `images` 文件夹一起传上去。

这时重新执行：

```powershell
git add .
git commit -m "add images"
git push
```

### 3. 文件名不一致

比如你写的是：

```text
image-01.png
```

但真实文件其实叫：

```text
image-01.PNG
```

这也可能导致问题。

---

## 如果后面要继续更新

以后你每次新增图片或新增案例，都可以重复下面这 3 步：

```powershell
git add .
git commit -m "update showcase"
git push
```

你可以把它理解成：

1. `git add .`：把这次修改加入准备区
2. `git commit -m "..."`：给这次修改做一次保存记录
3. `git push`：把这次保存上传到 GitHub

---

## 最推荐你的实际操作顺序

如果你现在要做第一次上传，我建议你按这个顺序走：

1. 注册并登录 GitHub
2. 新建仓库
3. 安装 Git
4. 配置 Git 用户名和邮箱
5. 整理本地 Markdown 和图片文件夹
6. 在 PowerShell 里进入项目目录
7. 执行 `git init`
8. 执行 `git remote add origin ...`
9. 执行 `git add .`
10. 执行 `git commit -m "first upload"`
11. 执行 `git branch -M main`
12. 执行 `git push -u origin main`
13. 回到 GitHub 页面检查显示效果

---

## 你现在这台电脑的实际情况

目前我已经确认，你现在的环境里 `git` 命令还不能直接使用。

这说明：

- 要么 Git 还没安装
- 要么已经安装了，但命令行还没识别到

所以你下一步最应该先做的是：

```powershell
git --version
```

如果这个命令报错，就先去安装 Git，然后再继续后面的上传流程。

---

## 最后给你的一个建议

第一次上传不要一次放太多内容。

你可以先用：

- 1 个 Markdown 文件
- 1 到 2 组图片案例

先成功完成第一次上传。等你确认整套流程跑通了，再慢慢往里面继续加内容。这样最稳，也最不容易出错。
