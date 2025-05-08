# Cursor 半透明背景 CSS (macOS)

该项目包含一个 CSS 文件 (`transparent-background-cursor.css`)，用于在 macOS 系统上为 Cursor 编辑器设置半透明的背景效果。

## 使用方法

1.  将本仓库中的 `transparent-background-cursor.css` 文件保存到您计算机上的一个固定位置 (例如，您可以创建一个像 `~/cursor-custom-css/` 这样的文件夹，并将 CSS 文件放在其中)。
2.  打开 Cursor 编辑器。
3.  打开用户设置的 JSON 文件。通常可以通过以下方式之一打开：
    - 使用快捷键 `Cmd + ,` (macOS) 或 `Ctrl + ,` (Windows/Linux) 打开设置界面，然后点击右上角的"打开设置 (JSON)"图标。
    - 通过命令面板 (`Cmd + Shift + P` 或 `Ctrl + Shift + P`) 搜索并选择 "Preferences: Open User Settings (JSON)"。
4.  在打开的 `settings.json` 文件中，找到或添加一个名为 `"vscode_vibrancy.imports"` (或者功能类似的自定义 CSS 导入配置项，具体名称可能因 Cursor 版本或您使用的相关透明/毛玻璃效果扩展而异) 的配置项。
5.  将您在步骤 1 中保存的 `transparent-background-cursor.css` 文件的**完整绝对路径**添加到该配置项的数组中。
    例如：
    ```json
    {
      // ... 其他设置 ...
      "vscode_vibrancy.imports": [
        "/Users/your_username/cursor-custom-css/transparent-background-cursor.css"
      ]
      // ... 其他设置 ...
    }
    ```
    如果您已经有其他自定义 CSS 文件列表，请将新路径添加到现有数组中：
    ```json
    {
      // ... 其他设置 ...
      "vscode_vibrancy.imports": [
        "/path/to/your/other-custom.css",
        "/Users/your_username/cursor-custom-css/transparent-background-cursor.css"
      ]
      // ... 其他设置 ...
    }
    ```
    **请确保将示例路径替换为您自己的实际文件路径。**
6.  保存 `settings.json` 文件。
7.  为了使更改完全生效，您可能需要重新加载 Cursor 窗口 (通过命令面板搜索 "Developer: Reload Window") 或重启 Cursor。

## 注意

- 此 CSS 主要针对 macOS 上的 Cursor 进行测试和设计。
- 编辑器的不同主题或将来的 Cursor 更新可能会影响此 CSS 的效果。如果遇到问题，你可能需要调整 CSS 规则。
