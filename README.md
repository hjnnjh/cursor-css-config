# Cursor 半透明背景 CSS (macOS)

该项目包含一个 CSS 文件 (`transparent-background-cursor.css`)，用于在 macOS 系统上为 Cursor 编辑器设置半透明的背景效果。

## 前提条件

- **安装 "Vibrancy Continued" 扩展**:
  1. 在 Cursor 编辑器中，打开扩展视图 (通常是侧边栏的方块图标，或使用快捷键 `Cmd+Shift+X` / `Ctrl+Shift+X`)。
  2. 搜索 "Vibrancy Continued"。
  3. 点击安装并确保其已启用。

## 使用方法

1.  **将 CSS 文件保存到本地**:
    将本仓库中的 `transparent-background-cursor.css` 文件保存到您计算机上的一个固定位置 (例如，您可以创建一个像 `~/cursor-custom-css/` 这样的文件夹，并将 CSS 文件放在其中)。

2.  **打开用户设置 (JSON)**:

    - 使用快捷键 `Cmd + ,` (macOS) 或 `Ctrl + ,` (Windows/Linux) 打开设置界面，然后点击右上角的"打开设置 (JSON)"图标。
    - 或通过命令面板 (`Cmd + Shift + P` 或 `Ctrl + Shift + P`) 搜索并选择 "Preferences: Open User Settings (JSON)"。

3.  **配置 CSS 导入路径**:
    在打开的 `settings.json` 文件中，找到或添加一个名为 `"vscode_vibrancy.imports"` (或者功能类似的自定义 CSS 导入配置项，具体名称可能因 Cursor 版本或您使用的相关透明/毛玻璃效果扩展而异，但对于 "Vibrancy Continued" 通常是这个) 的配置项。将您在步骤 1 中保存的 `transparent-background-cursor.css` 文件的**完整绝对路径**添加到该数组中。
    例如:

    ```json
    {
      // ... 其他设置 ...
      "vscode_vibrancy.imports": [
        "/Users/your_username/cursor-custom-css/transparent-background-cursor.css"
      ]
      // ... 其他设置 ...
    }
    ```

    如果您已经有其他自定义 CSS 文件列表，请将新路径添加到现有数组中:

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

4.  **保存设置**:
    保存 `settings.json` 文件。

5.  **重新加载窗口**:
    通过命令面板 (`Cmd + Shift + P` 或 `Ctrl + Shift + P`) 搜索并选择 "Developer: Reload Window"。这一步是为了让 Cursor 读取到 `settings.json` 的改动。

6.  **重新应用毛玻璃效果**:
    - 打开命令面板 (`Cmd + Shift + P` 或 `Ctrl + Shift + P`)。
    - 搜索并运行 "Vibrancy Continued: Reload" 或类似命令 (例如 "Enable Vibrancy")。该命令由 "Vibrancy Continued" 扩展提供，用于重新应用毛玻璃效果并加载自定义 CSS。
    - 如果找不到确切命令，请查阅 "Vibrancy Continued" 扩展的文档或设置，了解如何刷新或重新启用其效果。

## 注意

- 此 CSS 主要针对 macOS 上的 Cursor 进行测试和设计。
- 编辑器的不同主题或将来的 Cursor 更新可能会影响此 CSS 的效果。如果遇到问题，你可能需要调整 CSS 规则。
