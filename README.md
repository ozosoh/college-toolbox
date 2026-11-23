# 🚀 College Toolbox - 网课/作业防禁贴神器

> 绕过网页“禁止粘贴”限制，模拟真人打字速度自动输入。拒绝手酸，解放双手！

![GitHub stars](https://img.shields.io/github/stars/ShuhaoZHNG/college-toolbox?style=social)
![Python version](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## 💡 痛点背景

很多在线考试、网课作业系统为了防止作弊，禁用了 `Ctrl+V`。面对大段需要填写的文字，手打太累，效率极低。

**College Toolbox** 为你解决这个问题！它通过模拟键盘输入（像真人打字一样），自动将你剪贴板里的文字输入到网页中。

## ✨ 功能特点

- **一键破解**：无视网页的禁止粘贴限制。
- **真人模拟**：模拟键盘敲击，防止被系统检测。
- **自定义速度**：可调节打字速度（请见源代码）。
- **轻量免安装**：提供打包好的 `.exe` 文件，双击即用。

## 🚀 快速开始

### 方法一：直接下载运行（推荐小白）

1. 前往本仓库的 [Releases](../../releases) 页面。
2. 下载最新版的 `ghost_typer.exe`。
3. 双击运行，根据提示操作即可。（*注意：软件由 Python 打包，部分杀毒软件可能误报，请添加信任*）

### 方法二：源码运行（适合开发者）

```bash
# 克隆仓库
git clone https://github.com/ShuhaoZHNG/college-toolbox.git

# 安装依赖
pip install -r requirements.txt

# 运行程序
python ghost_typer.py
```

(你也可以直接双击 run.bat 运行)

## ⚠️ 常见问题 (FAQ)

**Q: 为什么我的电脑报毒了？**
A: 因为程序使用了 pyautogui 模拟键盘输入，部分杀毒软件（如360）会将其误判为恶意脚本，请添加白名单。

**Q: 支持 Mac 吗？**
A: 支持，Mac 用户请直接使用 Python 源码运行。

## 📜 免责声明

本项目仅供编程学习与自动化技术研究使用。请勿用于任何违反学校规定、考试纪律或法律法规的场景。因使用本工具造成的一切后果由使用者自行承担。

## 🤝 贡献

欢迎提 Issue 或 PR！如果觉得好用，请给个 ⭐ Star 支持一下！
