## v0.0.2-poto-pbv0.36.9 (WIP)

- 给本项目弄pbv0.37.4里的安全修复
  - 分析 https://github.com/pocketbase/pocketbase/releases/tag/v0.37.4 中的安全修复：OAuth2链接预劫持漏洞修复、bcrypt假密码检查改进。
  - 经查找，关于pb官方的具体修复提交是 https://github.com/pocketbase/pocketbase/commit/ca7cf1162ff429070e4672f6b221386c1db2c376


## v0.0.2-poto-pbv0.36.9

- 这是 PocketTogether 维护的 PocketBase 的首个正式构建版本。
- 基于官方 PocketBase v0.36.9，并使用和官方相同的构建流水线重新编译、打包与发布。
- 代码来源于 v0.36.9 即 commit： 58f605e90c4265db041dea724429a8fd335a6b9d
- 重新创建仓库而非 fork，避免官方仓库 ~200MB 的历史包袱
- 版本号说明 v0.0.1-poto-pbv0.36.9
  - v0.0.1 — PocketTogether 自身的发行版本号
  - poto — PocketTogether 标识
  - pbv0.36.9 — 基于 PocketBase v0.36.9