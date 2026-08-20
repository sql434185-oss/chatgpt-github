# GitHub 工具

以下三个开源项目已安装在本机，并通过 Codex 技能 `github-tools` 接入，Codex 可以直接调用。

## markitdown

- 项目：<https://github.com/microsoft/markitdown>
- 用途：把 Office 文档、网页、CSV 等常见格式转成 Markdown
- 版本：0.1.7
- 示例：`markitdown 文档.docx -o 文档.md`

## yt-dlp

- 项目：<https://github.com/yt-dlp/yt-dlp>
- 用途：从 YouTube、Bilibili 等支持的网站下载视频和音频
- 版本：2026.08.19
- 示例：`yt-dlp -f "bv*+ba/b" --merge-output-format mp4 <视频地址>`

## sherlock

- 项目：<https://github.com/sherlock-project/sherlock>
- 用途：按用户名检查公开社交账号是否存在
- 版本：0.16.0
- 示例：`sherlock <用户名>`
- 完整教程：[docs/sherlock-tutorial.md](docs/sherlock-tutorial.md)

### Sherlock 已新增的国内站点

已加入本机站点列表：Gitee、博客园（CNBlogs）、语雀（Yuque）。Sherlock 默认从官方远程清单加载站点，因此搜索这些国内站点时需要加 `--local`：

```powershell
sherlock --local --site Gitee 用户名
sherlock --local --site CNBlogs 用户名
sherlock --local --site Yuque 用户名
```

抖音、微博、知乎、小红书、Bilibili 等平台需要登录或依赖 JavaScript 渲染，或使用数字 ID，无法用当前方式可靠搜索。

升级 sherlock 后如发现国内站点丢失，需要在 `C:\Users\Shuqin\AppData\Local\Programs\Python\Python314\Lib\site-packages\sherlock_project\resources\data.json` 中重新加入以下条目：

```json
{
  "CNBlogs": { "errorType": "status_code", "url": "https://www.cnblogs.com/{}", "urlMain": "https://www.cnblogs.com/", "username_claimed": "dudu" },
  "Gitee": { "errorType": "status_code", "url": "https://gitee.com/{}", "urlMain": "https://gitee.com/", "username_claimed": "oschina" },
  "Yuque": { "errorType": "status_code", "url": "https://www.yuque.com/{}", "urlMain": "https://www.yuque.com/", "username_claimed": "yuque" }
}
```

## 环境

- 工具目录：`C:\Users\Shuqin\AppData\Local\Programs\Python\Python314\Scripts\`
- 媒体处理依赖：FFmpeg 9.0
