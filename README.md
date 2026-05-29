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
```


