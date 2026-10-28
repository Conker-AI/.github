<p align="center"><img src="https://raw.githubusercontent.com/Conker-AI/conker/main/dashboard/public/conker.png" width="96" alt="Conker" /></p>
<h1 align="center">Conker</h1>
<p align="center"><b>A personal AI companion you host yourself.</b><br/>
It remembers you, shows its work, and never acts without your say.</p>

<p align="center">
  <a href="https://github.com/Conker-AI/conker">Get started</a> ·
  <a href="https://github.com/Conker-AI/conker/blob/main/docs/2-how-it-works.md">How it works</a> ·
  <a href="https://github.com/Conker-AI/conker/blob/main/docs/status.md">What works today</a>
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Conker-AI/conker/main/docs/images/home-dark.png" />
  <img src="https://raw.githubusercontent.com/Conker-AI/conker/main/docs/images/home.png" alt="Conker's Home screen: what needs you, plan allowance and what's coming up" />
</picture>

Conker is an everyday AI chat that runs on your own server. It remembers across conversations,
runs your cron jobs, and acts through tools. What it may do is your setting, per chat, agent and
tool, and anything that needs you waits in one Inbox until you answer.

It is built as small services with one job each, so every boundary is a process boundary:

```mermaid
flowchart LR
    You([You]) --> GW[Gateway] --> Pi[Pi<br/>conversations]
    Pi --> MG[MemoryGate<br/>remembers]
    Pi --> TG[ToolGate<br/>acts, as allowed]
    Pi --> SG[SystemGate<br/>observes]
    MG --> EM[Embeddings]
```

| Repository | Job | Release |
|---|---|---|
| [**conker**](https://github.com/Conker-AI/conker) | The app, installer, deployment and docs. Start here. | |
| [**pi**](https://github.com/Conker-AI/pi) | Conversations, model roles, the gateway and a record of every turn | <img src="https://img.shields.io/github/v/tag/Conker-AI/pi?sort=semver&label=" alt="Pi release" /> |
| [**toolgate**](https://github.com/Conker-AI/toolgate) | The only way to act: typed tools, exact approvals, spending limits, the sandbox | <img src="https://img.shields.io/github/v/tag/Conker-AI/toolgate?sort=semver&label=" alt="ToolGate release" /> |
| [**memorygate**](https://github.com/Conker-AI/memorygate) | Memory with sources: evidence in, bounded context out | <img src="https://img.shields.io/github/v/tag/Conker-AI/memorygate?sort=semver&label=" alt="MemoryGate release" /> |
| [**systemgate**](https://github.com/Conker-AI/systemgate) | A read-only view of the machine | <img src="https://img.shields.io/github/v/tag/Conker-AI/systemgate?sort=semver&label=" alt="SystemGate release" /> |
| [**embeddings**](https://github.com/Conker-AI/embeddings) | Text to vectors, and nothing else | <img src="https://img.shields.io/github/v/tag/Conker-AI/embeddings?sort=semver&label=" alt="Embeddings release" /> |

Each service is licensed under AGPL-3.0 and usable on its own. Conker is early: see
[status](https://github.com/Conker-AI/conker/blob/main/docs/status.md) for what is proven and what
is still missing.
