> # 🧹 Windows 垃圾清理工具  
**一键安全清理临时文件、浏览器缓存与回收站，支持“预览模式”零风险运行。**

---

## 📦 下载与安装
1. 克隆或下载本仓库。  
2. 确保已安装 **Python 3.8+**。  
3. 安装依赖（仅需一次）：
   ```bash
   pip install -r requirements.txt
   ```
   依赖列表：`send2trash`, `winshell`, `psutil`

---

## 🚀 快速开始
| 场景 | 命令 |
|---|---|
| **先预览**（推荐第一次） | `python cleaner.py` |
| **正式清理** | 以**管理员身份**打开 PowerShell / CMD，执行：<br>`python cleaner.py --run` |

> ⚠️ **重要提示**  
> • `--run` 会**真正删除文件**，请先预览确认。  
> • 清理浏览器缓存时请**关闭所有浏览器窗口**。  
> • 若弹出 UAC 授权，请选择“是”。

---

## 🛡️ 安全机制
- **预览模式**：默认仅列出待删除项，不触碰任何文件。  
- **白名单**：自动跳过系统关键目录（如 `System32`、`WinSxS`）。  
- **回收站保护**：先移至回收站，30 天内可在回收站还原。  
- **占用检测**：跳过被其他程序锁定的文件，避免崩溃。  
- **二次确认**：执行 `--run` 时会再次询问 `y/n`。

---

## 🧩 支持清理项目
| 项目 | 路径示例 |
|---|---|
| 系统临时文件 | `%TEMP%`, `%TMP%`, `C:\Windows\Temp` |
| Chrome 缓存 | `%LOCALAPPDATA%\Google\Chrome\User Data\*\Cache` |
| Edge 缓存 | `%LOCALAPPDATA%\Microsoft\Edge\User Data\*\Cache` |
| 回收站 | 所有磁盘 `$Recycle.Bin` |

---

## 📋 常见问题
**Q1：误删了文件怎么办？**  
A：所有删除操作均通过 `send2trash` 移至回收站，打开回收站即可还原。

**Q2：需要每次都管理员权限吗？**  
A：仅清理系统级目录（如 `C:\Windows\Temp`）时需要；普通用户缓存目录无需管理员。

**Q3：可以清理 Firefox 吗？**  
A：当前版本未内置，可手动在 `clean_browser_cache()` 中添加 Firefox 路径后使用。

---

## 📝 日志与反馈
- 日志文件：`cleaner.log`（与脚本同目录）。  
- 遇到问题请带上日志文件提交 [Issue](../../issues)。


---

**一键清爽，立即体验！**
