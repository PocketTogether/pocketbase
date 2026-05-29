原README：[README-pocketbase.md](./README-pocketbase.md)

fork了pocketbase，尝试自己构建
- https://github.com/pocketbase/pocketbase
- https://github.com/haruki1953/pocketbase

基于版本 v0.36.9，最后的 commits 是 58f605e90c4265db041dea724429a8fd335a6b9d
- https://github.com/pocketbase/pocketbase/tree/v0.36.9
- https://github.com/pocketbase/pocketbase/commits/v0.36.9/
- https://github.com/pocketbase/pocketbase/commit/58f605e90c4265db041dea724429a8fd335a6b9d

创建分支 haruki/pbv-0-36-9

尝试理解 `.github\workflows\release.yaml`

尝试push，观察 github action 

尝试带版本号push，观察 Releases
```
v0.0.0-haruki-pbv0.36.9
创建标签并推送

哦哦哦，我明白了，github actions 被带标签的推送触发后，会创建草稿 Release，自己只需编辑文本然后点击 Publish release 即可
```

尝试git清理，减小仓库大小

使用组织 PocketTogether 再创建新仓库，不选择fork而是直接用文件创建，因为 pocketbase/pocketbase 其实有点问题，它的git有点大，将近200MB
- https://github.com/haruki1953/pocketbase
- https://github.com/PocketTogether/pocketbase

正式发布将用于PocketTogether旗下项目的pocketbase
```
v0.0.0-poto-pbv0.36.9

失败了
对于组织，好像要开启工作流读写权限
https://github.com/organizations/PocketTogether/settings/actions
Workflow permissions
Read and write permissions

v0.0.1-poto-pbv0.36.9

彻底成功（
```


# PocketTogether PocketBase Distribution  
基于 PocketBase v0.36.9 的独立构建版本

## 📌 项目简介
PocketTogether 维护的 PocketBase 构建版本，基于官方 PocketBase **v0.36.9**，并使用和官方相同的构建流水线重新编译、打包与发布。  
目标是为 PocketTogether 旗下项目提供：

- 稳定、可控的 PocketBase 运行时  
- 可复现的构建产物  
- 清晰的版本号体系  
- 更轻量的仓库体积（避免官方仓库 200MB 的历史包袱）

本仓库不是官方 fork，而是基于官方源码重新创建的轻量仓库，适合长期维护。

---

## 🏗 构建来源

本版本基于官方 PocketBase：

- 版本：**v0.36.9**  
- 最后 commit：`58f605e90c4265db041dea724429a8fd335a6b9d`  
- 官方仓库：  
  - https://github.com/pocketbase/pocketbase
  - https://github.com/pocketbase/pocketbase/tree/v0.36.9

---

## 🚀 构建与发布流程

### 1. 使用 GitHub Actions 自动构建
仓库包含 `.github/workflows/release.yaml`，当推送带标签的 commit 时自动触发构建：

```
git tag v0.0.1-poto-pbv0.36.9
git push origin v0.0.1-poto-pbv0.36.9
```

GitHub Actions 会：

- 自动构建多平台二进制  
- 生成 checksums  
- 创建 Draft Release（草稿）  

然后管理者手动点击 “Publish release” 即可发布  

### 2. 组织仓库权限
PocketTogether 组织需要开启：

> Settings → Actions → Workflow permissions → **Read and write permissions**

否则构建无法创建 Release。

---

## 📦 构建产物

每次 Release 包含：

- `pocketbase` 可执行文件（Linux / macOS / Windows）
- `checksums.txt`
- `LICENSE.md`
- `CHANGELOG.md`

所有产物均由 goreleaser 自动生成。

---

## 🔖 版本号规范

PocketTogether 使用以下版本格式：

```
vA.B.C-poto-pbvX.Y.Z
```

示例：

```
v0.0.1-poto-pbv0.36.9
```

含义：

- `v0.0.1` — PocketTogether 自身的发行版本号  
- `poto` — PocketTogether 标识  
- `pbv0.36.9` — 基于 PocketBase v0.36.9  

---

## 🧩 与官方 PocketBase 的关系

本仓库：

- **保持 module 名称不变**：`github.com/pocketbase/pocketbase`  
- **保持 import 路径不变**  
- **保持 API 行为一致**  
- **仅构建与发布，不修改核心逻辑**

