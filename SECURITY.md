# 安全问题 · Security

## 怎么报告

发现安全问题，请**不要**开公开的议题，也不要在合并请求里讨论。

到对应仓库页面的 **Security → Report a vulnerability**，私下告诉我们。只有维护者看得到这份报告。

写清楚这几样，我们能更快定位：

- 哪个仓库、哪个版本（或提交号）
- 问题是什么，能造成什么后果（比如能绕过限制、能读到不该读的数据）
- 怎么重现，最好一步一步写
- 你想到的修法（可选）

## 之后会怎样

我们会尽快回复，确认问题后先私下修好、发新版本，再公开说明。如果你愿意，公开时会写上你的名字表示感谢。

这些都是个人维护的开源项目，没有悬赏，也没法承诺固定的回复时间，但安全问题会优先处理。

## 哪些算

各仓库说明里写的安全承诺被打破了，都算。比如：

- 船长派活：选手绕过隔离，写到副本以外的地方、读到密钥或登录文件、改到各家的全局配置
- 船长密码箱：不用主密码就能读到保险库内容，或者密码被明文写到磁盘上
- 船长运维：绕过危险命令拦截、越权操作、没有权限的人改掉或删掉审计记录
- 船长 K8s：不用 Token 就能操作集群，或者做到了登录所用 Token 的 RBAC 权限之外的事
- 船长待办：数据被发到本机以外的地方

用默认密码、默认密钥原样上线导致的问题不算漏洞，各仓库说明里已经写了上线前要改。

---

## Reporting

Please **don't** open a public issue or discuss it in a pull request. Use **Security → Report a vulnerability** on the repository page; only maintainers can see it. Include the repository and version (or commit), what the problem is and what it lets someone do, steps to reproduce, and a suggested fix if you have one.

We'll reply as soon as we can, fix it privately, release, and then disclose, crediting you if you'd like. These are personally maintained projects with no bounty and no guaranteed response time, but security reports come first.

Anything that breaks a safety promise made in a repository's README counts, e.g. a Captain Agents worker escaping its sandbox, reading a Captain Password vault without the master password, bypassing Captain Ops command blocking or tampering with its audit log without permission. Problems caused by running default passwords or keys in production are not vulnerabilities; each README says to change them first.
