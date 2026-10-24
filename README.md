# codex-capacity-build

个人用的 codex 构建仓库，跟随 [openai/codex](https://github.com/openai/codex) 上游自动出 Windows 版本。

- 构建：`upstream-sync` 工作流每 6 小时检查上游 release，有新版就自动构建并发布
- 补丁：`patches/codex.patch`
- 用法：用 release 里的 `codex.exe` 覆盖 npm 包内嵌的同版本二进制；恢复官方：`npm i -g @openai/codex@<版本>`
- 开关：`CODEX_CAPACITY_RETRY_FAST=0`
