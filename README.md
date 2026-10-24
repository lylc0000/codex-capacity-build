# codex-capacity-build

自动给官方 [openai/codex](https://github.com/openai/codex) 打"容量错误快速重试"补丁并编译 Windows 版。

- 补丁：`patches/capacity-retry.patch`（只改 `codex-rs/core/src/responses_retry.rs` 和它的测试文件）
- 流程：每 6 小时检查官方新版 release → 克隆对应 tag → 套补丁 → 格式检查 + 定向测试 ∥ release 编译 → 全部通过后发 [Releases](https://github.com/lylc0000/codex-capacity-build/releases)
- 套不上补丁（上游重构了重试模块）：自动开 issue 提醒，更新补丁文件后手动重跑工作流即可
- 产物用法：用 release 里的 `codex.exe` 覆盖 npm 包内嵌的同版本二进制；恢复官方：`npm i -g @openai/codex@<版本>`
- 关闭快速重试：环境变量 `CODEX_CAPACITY_RETRY_FAST=0`

