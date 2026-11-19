# 索尼相机工具箱 · Sony Camera Tool v1.0.1

> 本版本含相机 App 写入功能。当前验证仅覆盖离线代码、构建和打包，不代表任何相机上的安全性或功能验收。

## 下载与校验

| 文件 | 大小 | SHA-256 |
|---|---:|---|
| [`SonyCameraTool_v1.0.1.zip`](https://github.com/mingwucn/SonyCameraTool_Download/releases/download/v1.0.1/SonyCameraTool_v1.0.1.zip) | 32,106,759 bytes | `79bbc64148f88c2bb974d40420910035696e0af87fe3cd83ab3e9d3f3f4ec419` |
| `SonyCameraTool_v1.0.1_BUILD_MANIFEST.json` | 随发布附件提供 | 清单含版本、源码状态、可执行文件和 ZIP 哈希，以及 49 个随包载荷的来源与哈希 |

## v1.0.1 变更

- 修复 SonyCameraTool_Download [issue #2](https://github.com/mingwucn/SonyCameraTool_Download/issues/2) 所报告的还原方向错误：还原计划现在写入计划的目标字节并按该目标验证。
- 逐项记录读取偏移、实读字节、目标字节和写入/跳过决定。事务备份区分相机实读前值和计划目标值。
- 为 Windows 字体变更通知增加超时，避免应用启动被其他无响应窗口阻塞。
- 界面说明现限定为所选 App 目标；移除了“100% 恢复”、未经证实的 60 秒闪存提交说明及仅凭状态提示重绑 WinUSB 的指引。

## α6700 Playback FTP 状态

机主报告 Network FTP 已配置并可工作。在机主最近一次 C1/C2 Playback Custom Key picker 检查中，**FTP Trans. (This Img.)** 可选，**FTP Transfer** 未出现在列表中。v1.0.1 没有启用或修复后一项；其 App 候选仍只是未安装、未验证的离线参考。没有进行按键分配持久性或 FTP 接收端到端测试。

## 验证边界

- Python 3.10.20 / PyInstaller 6.22.3 构建成功；8 项 `camera_tool_backend` 测试通过。
- 冻结包 `--self-check`、`--describe`、`--gui-self-check` 均通过；49 个随包载荷哈希匹配来源清单。
- 本候选没有连接相机，没有运行服务/原生相机辅助程序，没有更改 App 或 WBI，没有执行 FTP 传输，也没有触发 CI/CD。
- 离线构建结果不替代独立代码审查或相机实测。Issue #2 仍待独立审查和设备验收；新版本发布前请以发布页为准。

本项目的当前公开下载页为 [SonyCameraTool_Download](https://github.com/mingwucn/SonyCameraTool_Download)。请以发布页上的版本和校验值为准。
