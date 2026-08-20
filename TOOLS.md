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

## 环境

- 工具目录：`C:\Users\Shuqin\AppData\Local\Programs\Python\Python314\Scripts\`
- 媒体处理依赖：FFmpeg 9.0
