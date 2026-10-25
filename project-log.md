# 项目会话日志

## 2026-10-25 — ChinaMax 与 AI 窄补丁
<!-- project-log-id: shadow-20261025-chinamax-ai -->

- 状态：配置已改，待推送到远程并在客户端更新验证。
- 范围：Shadowrocket.conf、project-log.md。
- 任务背景：对照社区分流方案，补强国内域名覆盖，并为 AI 策略组叠加 Claude / Gemini / BardAI 窄规则集。
- 线上资源：[GitHub 仓库](https://github.com/Bapexboz/shadowrocket-config)。
- 实际完成：`China.list` 替换为 `ChinaMax.list`；在 LingJingMaster `AI.list` 后追加 blackmatrix7 的 Claude、Gemini、BardAI；保留个人域名与 GEOIP,CN。
- 决策与口径：不采用整包 bm7 OpenAI.list，避免 auth0/intercom 等宽匹配；Google 规则暂不迁移。
- 本地产物：Shadowrocket.conf。
- 待确认 / 下一步：Shadowrocket 更新远程配置后，抽查国内站直连与 Claude/Gemini 出口。

## 2026-10-19 — 修复 Typora 直连与系统 DNS 回退
<!-- project-log-id: shadow-20261019-typora-dns -->

- 状态：已验证完成并推送到远程仓库。
- 范围：Shadowrocket.conf、project-log.md。
- 任务背景：用户排查 Typora 2 官网（v2.typora.io）打不开的问题，发现漏网之鱼走代理超时，且内网环境下外部公共 DNS 被封禁导致 DIRECT 解析死锁。
- 线上资源：[GitHub 仓库](https://github.com/Bapexboz/shadowrocket-config)。
- 实际完成：`Shadowrocket.conf` 中配置 `fallback-dns-server = system`；为 `typora.io` 添加 `DOMAIN-SUFFIX,typora.io,DIRECT` 规则，并在 `[Host]` 与 `always-real-ip` 中绑定系统 DNS 解析；同步 LinkedIn 规则。
- 决策与口径：内网环境直连域名优先走系统内网 DNS 解析，绕过公共 DNS 阻断；客户端手动生效后远端仓库同步保持一致。
- 本地产物：Shadowrocket.conf。
- 待确认 / 下一步：无。

## 2026-10-14 — 更新住宅节点分组与 TypeSafe 分流
<!-- project-log-id: shadow-20261014-routing -->

- 状态：配置修改和静态检查完成；客户端更新后的实际网络连通性待验证。
- 范围：Shadowrocket.conf、Whitelist.conf。
- 任务背景：用户已停订 SolaDrive，要求将原有默认选择转到 TmhHost，并指定代码托管走 V.PS 东京。
- 线上资源：[GitHub 仓库](https://github.com/Bapexboz/shadowrocket-config)，用于远程配置更新。
- 实际完成：删除 SolaDrive 分组、成员和注释；保留 TypeSafe 域名后缀规则并统一归入 AI 服务；AI 默认 TmhHost、代码托管默认 V.PS；检查分组成员、默认选择、规则策略引用和重复成员，通过 git diff --check。
- 决策与口径：使用准确名称 TmhHost LA Hysteria2、TmhHost LA REALITY、V.PS Tokyo Hysteria2、V.PS Tokyo REALITY；节点凭据仍由客户端保存。静态引用检查不代表节点可连接。
- 本地产物：两份配置文件与本日志。
- 待确认 / 下一步：在 Shadowrocket 更新远程配置，核对已保存的策略选择，再验证 TypeSafe API 与 GitHub 连通性。
