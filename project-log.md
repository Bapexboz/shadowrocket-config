# 项目会话日志

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
