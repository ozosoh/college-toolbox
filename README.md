# 🚀 College Toolbox - 网课/作业防禁贴神器

> 绕过网页“禁止粘贴”限制，模拟真人打字速度自动输入。拒绝手酸，解放双手！

![GitHub stars](https://img.shields.io/github/stars/ShuhaoZHNG/college-toolbox?style=social)
![Python version](https://img.shields.io/badge/python-3.8%2B-blue)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)
![License](https://img.shields.io/badge/license-MIT-green)

## 💡 痛点背景

很多在线作业、网课作业系统为了防止粘贴，禁用了 `Ctrl+V`。面对大段需要填写的文字，手打太累，效率极低。

**College Toolbox** 为你解决这个问题！它不往剪贴板里粘贴，而是把每个字当成“用键盘敲出来的”，逐字发送到当前光标所在的输入框中。

## ✨ 功能特点

- **不走粘贴**：直接向焦点控件发送按键事件，网页的粘贴拦截对其无效。
- **逐字上屏**：基于 Win32 `SendInput` + `KEYEVENTF_UNICODE`，中文和 emoji 也能像输入法一样逐字上屏。
- **节奏可调**：每字间隔、随机波动、中文额外延时、标点停顿都能在界面上改，敲击间隔带随机抖动，不是机械匀速。
- **全局热键**：写好内容后，光标点进目标框，按 `*` 开始；再按 `*` 或 `Esc` 立即停止。
- **焦点保护**：键入过程中一切换窗口就自动停止，避免把字打进别的地方。
- **纯标准库**：只用 `ctypes` + `tkinter`，**不需要安装任何第三方包**，克隆下来直接跑。

## 🚀 快速开始

### 环境要求

- **Windows**（核心功能依赖 Win32 API，当前版本在 macOS / Linux 上会直接退出）
- **Python 3.8+**，安装时勾选 `tcl/tk and IDLE`（界面依赖 tkinter）
- 无需 `pip install` 任何东西

### 方法一：源码运行（推荐）

```bash
# 克隆仓库
git clone https://github.com/ShuhaoZHNG/college-toolbox.git

# 直接运行，无需安装依赖
python ghost_typer.py
```

也可以直接双击 `run.bat`。如果目标软件是以管理员身份运行的，请双击 `run_as_admin.bat`，否则按键会被系统拦截。

### 方法二：自己打包成 exe（可选）

```bash
pip install pyinstaller
pyinstaller -F ghost_typer.py
```

打包完成后在 `dist/` 里拿到 `ghost_typer.exe`。本仓库暂未提供现成的 exe 文件，首次运行前需自行打包。

## 🕹 使用步骤

1. 在窗口文本框里写好要输入的内容，或点“从 txt 载入”导入文本文件。
2. 点进目标网页 / 软件的输入框，让光标就位。
3. 按 `*`（主键盘 Shift+8 或小键盘 `*`）开始逐字键入；也可以点“▶ 开始（3 秒后）”按钮，给自己留切窗口的时间。
4. 中途再按 `*` 或 `Esc` 立即停止。

## ⚙ 参数说明

| 参数 | 默认值 | 作用 |
| --- | --- | --- |
| 每字间隔 ms | 90 | 字符之间的基础间隔 |
| 随机波动 % | 35 | 在基础间隔上下浮动，避免节奏均匀得不自然 |
| 中文额外 ms | 45 | 非 ASCII 字符额外延时 |
| 标点停顿 ms | 180 | 标点、换行后额外停顿 |

输入方式有两种：**Unicode 直发**（默认，推荐）和 **剪贴板逐字粘贴**（兼容模式，逐个字符写入剪贴板再 Ctrl+V，适用于远程桌面、部分终端等不接受 Unicode 按键的程序；会临时占用剪贴板，每字至少 0.1 秒，剪贴板里是图片 / 文件时会被阻止启动）。

## ⚠ 常见问题（FAQ）

**Q: 为什么我的电脑报毒了？**
A: 本程序会安装全局键盘钩子并向其他窗口注入按键事件，这在杀软看来和键盘记录器的行为很像，因此容易被误判。加入白名单即可。

**Q: 输入没反应，一个字都没打出来？**
A: 多半是权限不对等——目标软件以管理员身份运行时，本程序也要以管理员身份启动（用 `run_as_admin.bat`），否则 Windows 的 UIPI 会拦下所有按键注入。其次确认光标确实在目标输入框里。

**Q: 支持 Mac / Linux 吗？**
A: 不支持。核心逻辑依赖 Windows 的 `SendInput` 与 `WH_KEYBOARD_LL` 全局钩子，非 Windows 系统启动时会直接提示退出。

**Q: 中文和 emoji 能打吗？**
A: 能。Unicode 直发模式不依赖输入法，按 Unicode 码位逐个上屏；兼容模式也能处理。

**Q: 仓库里的 zip 是什么？**
A: `逐字输入模拟.zip` 是早期旧版本，新功能以 `ghost_typer.py` 为准。

## 📜 免责声明

本项目仅供编程学习与自动化技术研究使用。请勿用于任何违反学校规定、课程要求或法律法规的场景。因使用本工具造成的一切后果由使用者自行承担。

## 🤝 贡献

欢迎提 Issue 或 PR！如果觉得好用，请给个 ⭐ Star 支持一下！
