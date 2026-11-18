# Adaptive Taskbar Transparency (自适应透明任务栏)

A [Windhawk](https://windhawk.net/) mod for Windows 11 that makes the taskbar adapt to what's on screen:

| Situation | Default style |
| --- | --- |
| Desktop / no large windows | Clear (fully transparent) |
| Maximized, fullscreen, or snapped window | Acrylic |
| Start, search, task view, notification / quick settings flyouts | Windows default |

Every state's style can be changed in the mod's settings (clear, blur, acrylic, Windows default, or keep the existing style).

## What's different from Dynamic Taskbar Transparency

This mod is based on [Dynamic Taskbar Transparency](https://windhawk.net/mods/dynamic-taskbar-transparency) v0.3.9 by [11581](https://github.com/r1file) and adds:

- **Snapped windows count as maximized.** Windows snapped with Snap Layouts, Win+Arrow or PowerToys FancyZones that touch the taskbar edge and cover most of the screen height switch the taskbar out of the clear state. The coverage percentage and edge tolerance are configurable.
- **Excluded programs.** List process names (e.g. `mspaint.exe`) whose windows should never make the taskbar opaque.
- **Toast notifications are ignored.** A popup notification no longer briefly switches the taskbar to the flyout style.
- Chinese labels in the settings UI.

These changes have also been proposed upstream: [ramensoftware/windhawk-mods#7599](https://github.com/ramensoftware/windhawk-mods/issues/7599).

## Install

1. Install [Windhawk](https://windhawk.net/).
2. In Windhawk, click **Create a new mod**, replace the editor contents with [`adaptive-taskbar-transparency.wh.cpp`](adaptive-taskbar-transparency.wh.cpp), and click **Compile Mod**.
3. The first time, Windhawk downloads Windows symbols for `taskbar.view.dll`, which can take a minute or two. After that it loads instantly, including after reboots.

Don't run it together with TranslucentTB or another tool that changes the taskbar background.

## Status

Tested so far on Windows 11 with a single bottom taskbar: the clear desktop state works. Snapped-window detection and the notification fix are still being tested. Issues and feedback are welcome.

## License

GPL-3.0, same as the original mod. See [LICENSE](LICENSE).

---

## 中文说明

Windows 11 的 Windhawk 模组：桌面上任务栏全透明；有最大化、全屏或贴靠分屏窗口时变成亚克力毛玻璃；打开开始菜单、搜索、通知等系统界面时恢复 Windows 默认样式。每种情况的样式都能在设置里改。

基于 11581 的 Dynamic Taskbar Transparency v0.3.9 修改，新增：贴靠窗口算作最大化、排除程序列表、忽略通知弹窗，以及中文设置界面。

安装：装好 Windhawk 后点"创建新模组"，把编辑器内容换成 `adaptive-taskbar-transparency.wh.cpp` 的内容，点"编译模组"。第一次会下载符号文件，需要等一两分钟。

请不要和 TranslucentTB 同时使用。
