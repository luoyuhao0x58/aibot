# AI 使用环境打包

## 初始化

- 启动程序

```bash
# 获取代码
git clone xxx.git aienv && cd aienv
# 构建镜像
docker compose build
# 配置环境变量
echo '
CLAWHUB_TOKEN=xxx # 你 CLAWHUB 的 token，如果没有，可以去官网注册一个，否则不会在启动的时候安装一些有用的 SKILL
' > .env
# 启动容器
docker compose up -d
```

- openclaw 配置

```shell
# 进入容器
docker compose exec -it openclaw bash
# 配置模型（按提示按需选择）
openclaw configure --section model
# 配置渠道（按提示按需选择）
openclaw configure --section channels
```

- 其它配置（工具或者技能，可选）

`docker compose exec -it openclaw bash` 进入容器， 写入 `~/.openclaw/.env` 文件。

```shell
TAVILY_API_KEY=xxx  # 可选，用于 Tavily 搜索的 API
```

## 默认安装的工具

- chromium 用于智能体的网页浏览,已安装了CJK字体
- playwright 用于自动化浏览器操作

## 默认安装的 SKILL

- web-search-plus 用于提示搜索的体验