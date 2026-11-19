# artex-global-lzcapp

[ARTEX 国际版](https://github.com/jiwoochris/artex-global)（LLM 多智能体自动化渗透测试平台，AGPL-3.0）的懒猫微服打包（镜像模式，仓库 [lazycat-contrib/artex-global-lzcapp](https://github.com/lazycat-contrib/artex-global-lzcapp)，仅发布喵喵商店）。

> ⚠️ 仅限授权使用：只对自有系统或已获书面授权的目标测试。用途说明见上游 README 的安全声明与 Defense & Detection 指南。

## 说明

- 镜像模式：主服务 `ghcr.io/jiwoochris/artex-global`（CI 经 ghcr.1ms.run 加速 + digest 校验），数据库 `postgres:16-alpine`。
- 服务端口：Web 控制台 8787（HTTP 入口）、流量录制代理 8788（L4 ingress）。
- 管理员密码经部署参数注入 `ARTEX_ADMIN_PASSWORD` 首次初始化（跳过 /setup token）；登录页自动填充。
- LLM Key 可安装时预填或稍后在界面「LLM 设置」配置。
- 数据持久化：PostgreSQL 数据、应用数据（SQLite + jwt.key）、skills 目录。
- 已接入懒猫文件选择器拦截（报告/证据导出下载）。
- 升级：CI 定时检查上游 `vN.N.N-global.N` tag（映射为 SemVer），自动发版并发布喵喵商店。
