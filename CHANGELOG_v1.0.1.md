# Sony Camera Tool v1.0.1 — Release Notes

## Fixes

- **Issue #2, restore direction:** restore plans encode the currently patched bytes as the expected source and stock bytes as the destination. The old transaction selected the source bytes as its target, so it could report success without restoring the camera. Both apply and restore now write the planner's destination and verify that destination.
- **Transaction evidence:** logs identify each target offset, bytes read, requested bytes, and write/skip decision. Physical transaction backup records use the actual pre-read bytes and label the planned target separately; simulated records identify themselves as plan-derived.
- **Build startup check:** the Windows font-change broadcast now uses a bounded timeout. The build directs GUI self-check logs to temporary storage and refuses to package a `logs` directory.
- **Build provenance:** the manifest records the source revision and working-tree diff hash, Python/PyInstaller versions, executable and ZIP hashes, and hashes for the 49 payload files carried forward from the verified v1.0.0 public archive.
- **User-facing scope:** the GUI now describes selected App targets instead of promising a full FTP unlock or 100% restore, removes the unsupported 60-second persistence claim, avoids driver changes based only on status text, and states that shortcut delivery needs a camera/receiver check.

## Playback FTP finding

The owner reports Network FTP works. The latest picker observation is that `FTP Trans. (This Img.)` is selectable and `FTP Transfer` is absent. This candidate does not add the General Transfer shortcut. Its App-only reference candidate remains `REFERENCE_ONLY_NOT_INSTALLABLE`; it has no WBI target. C1/C2 assignment persistence, restart behavior, native key dispatch, and FTP receipt were not tested for this candidate.

## Validation record

- `python -B -X utf8 -m unittest discover -s tests -p test_camera_tool_backend.py -v`: **8 passed**.
- Frozen `--self-check`: **passed** (`camera_commands=0`).
- Frozen `--describe`: **passed**.
- Frozen `--gui-self-check`: **passed** (`CAMERA_COMMANDS=0`).
- ZIP inventory: internal and external manifests match; all 49 payload hashes match; required bundle files are present; no firmware App image, WBI dump, camera backup, photograph, or build log path is present.
- Build: Python **3.10.20**, PyInstaller **6.22.3**; ZIP SHA-256 `79bbc64148f88c2bb974d40420910035696e0af87fe3cd83ab3e9d3f3f4ec419`.
- Build validation performed no camera/service/helper access, App/WBI write, FTP/network transfer, or CI/CD operation.

This local validation does not close issue #2 or qualify a camera write. Independent review and device acceptance remain required before release promotion.

---

## 中文说明

### 修复

- **Issue #2 还原方向：** 还原计划把当前补丁值作为预期源值，把原厂值作为目标值。旧事务却把源值当作写入目标，因此可能不写入就报告成功。现在 apply 和 restore 都写入计划目标，并按目标回读验证。
- **事务证据：** 日志逐项记录偏移、实读字节、目标字节和写入/跳过决定。实体事务备份使用实际预读值，并单独标明计划目标；模拟记录标明其数据来自计划定义。
- **启动检查：** Windows 字体变更广播增加有界等待；构建时将 GUI 自检日志写到临时目录，并拒绝打包 `logs` 目录。
- **构建来源：** 清单记录源码修订、工作区差异哈希、Python/PyInstaller 版本、EXE/ZIP 哈希，以及从已验证 v1.0.0 公开包延用的 49 个载荷文件哈希。
- **界面文案：** 说明限定到所选 App 目标，不再承诺完整 FTP 解锁或 100% 还原；移除未经证实的 60 秒持久化说法和仅凭状态提示改驱动的指引，并明确快捷键收件需在相机/接收端验证。

### Playback FTP 现状

机主报告 Network FTP 可用。最近一次 picker 观察为 `FTP Trans. (This Img.)` 可选、`FTP Transfer` 缺失。本候选没有新增 General Transfer 快捷键；其 App 参考候选仍为 `REFERENCE_ONLY_NOT_INSTALLABLE`，没有 WBI 目标。本候选未验证 C1/C2 分配持久性、重启、原生按键分发或 FTP 收件结果。

### 验证记录

- 后端测试：**8 项通过**。
- 冻结包 `--self-check`、`--describe`、`--gui-self-check`：**全部通过**；自检未发送相机命令。
- ZIP 清单检查：内部与外部构建清单一致；49 个载荷哈希匹配；必需文件齐全；没有固件 App 镜像、WBI 转储、相机备份、照片或构建日志路径。
- Python **3.10.20**、PyInstaller **6.22.3**；ZIP SHA-256：`79bbc64148f88c2bb974d40420910035696e0af87fe3cd83ab3e9d3f3f4ec419`。
- 未访问相机/服务/辅助程序，未写 App/WBI，未执行 FTP/网络传输，未触发 CI/CD，也没有 GitHub 评论、PR 或发布。

离线验证不能关闭 issue #2，也不能替代相机写入验收。发布前仍需独立审查和设备验收。
