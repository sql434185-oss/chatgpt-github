# Sherlock 使用教程

Sherlock 是一个开源用户名搜索工具，可以检查同一个用户名在 400 多个公开社交平台和网站上是否存在。项目使用 MIT 协议，官方仓库位于 <https://github.com/sherlock-project/sherlock>。

## 本机安装信息

- 版本：0.16.0
- 命令位置：`C:\Users\Shuqin\AppData\Local\Programs\Python\Python314\Scripts\sherlock.exe`
- 官方站点：<https://sherlockproject.xyz/>

## 主要功能

- 检查用户名在哪些公开平台存在，并输出对应主页链接
- 一次搜索多个用户名
- 使用 `{?}` 占位符自动生成相似用户名变体（替换为 `_`、`-`、`.`）
- 导出为文本、CSV 或 Excel（xlsx）结果
- 只检查指定网站，减少等待时间
- 支持代理、Tor、自定义超时时间
- 支持加载自定义 JSON 站点列表
- 找到结果后可直接用浏览器打开

## 基本用法

搜索一个用户名：

```bash
sherlock user123
```

搜索多个用户名：

```bash
sherlock user1 user2 user3
```

搜索用户名变体（例如同时检查 `user_name`、`user-name`、`user.name`）：

```bash
sherlock user{?}name
```

## 常用参数

| 参数 | 作用 |
| --- | --- |
| `-o, --output <文件>` | 单个用户名时把结果保存到指定文件 |
| `-fo, --folderoutput <目录>` | 多个用户名时把结果保存到指定目录 |
| `--csv` | 生成 CSV 结果文件 |
| `--xlsx` | 生成 Excel 结果文件 |
| `--site <网站名>` | 只检查指定网站，可重复使用 |
| `--timeout <秒>` | 每次请求等待时间，默认 60 秒 |
| `--proxy <地址>` | 通过代理请求，例如 `socks5://127.0.0.1:1080` |
| `--tor` | 通过 Tor 请求（需要本机安装 Tor） |
| `--browse` | 用默认浏览器打开所有命中的结果 |
| `--print-found` | 把命中的结果也显示到终端 |
| `--print-all` | 显示所有网站结果，包括未命中的 |
| `--no-color` | 关闭终端彩色输出 |
| `--nsfw` | 额外检查 NSFW 网站（默认不检查） |
| `--ignore-exclusions` | 忽略上游排除规则（可能增加误报） |

完整参数可用 `sherlock --help` 查看。

## 实际示例（本机已验证）

只检查 GitHub 上的用户名 `octocat`：

```bash
sherlock --site github --timeout 20 octocat
```

本机运行结果：

```text
[*] Checking username octocat on:

[+] GitHub: https://www.github.com/octocat

[*] Search completed with 1 results
```

`[+]` 表示找到了对应的公开主页，`[-]` 表示在该平台没有找到。保存结果时，默认会生成以用户名为文件名的文本文件。

## 使用注意

- 该工具只检索公开信息，请勿用于骚扰、人肉搜索、密码破解或其他违法用途
- 不同平台可能对批量请求有限制，请合理设置 `--timeout` 并降低请求频率
- 需要匿名访问时再使用 Tor 或代理，普通使用不需要
- NSFW 网站默认被排除，明确需要时才使用 `--nsfw`

## 国内平台支持情况

本机已加入三个国内站点：Gitee、博客园（CNBlogs）、语雀（Yuque）。Sherlock 默认加载官方远程站点清单，所以搜索这些站点时要加 `--local`：

```bash
sherlock --local --site Gitee 用户名
sherlock --local --site CNBlogs 用户名
sherlock --local --site Yuque 用户名
```

抖音、微博、知乎、小红书、Bilibili 等主流平台暂时无法支持：它们需要登录或依赖 JavaScript 渲染，或者主页使用数字 ID，无法通过简单的用户名 URL 判断账号是否存在。
