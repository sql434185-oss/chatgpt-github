# ChatGPT × GitHub 互通

这个仓库由 Codex 自动接入 GitHub，实现本机工作区与 GitHub 仓库之间的双向互通。

## 已接入内容

- GitHub 账号：`sql434185-oss`
- 远程仓库：`chatgpt-github`
- 默认分支：`main`

## 常用命令

```bash
git pull      # 从 GitHub 拉取最新内容
git push      # 把本机改动推送到 GitHub
git status    # 查看当前工作区状态
```

## 工作方式

本机目录与 GitHub 仓库通过 `origin` 远程关联。每次在本机提交并推送后，GitHub 上会立即看到更新；从 GitHub 拉取或修改后，本机也能同步回来。
