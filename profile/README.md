<div align="center">

<img src="assets/banner.png" alt="Secret Store — Banner" width="100%" />

# 🔐 Secret Store

### Plataforma SaaS modular para venda e aluguel de bots Discord

**Bots configuráveis · Multi-tenant · Marketplace de módulos · Runtime distribuído · Segurança crítica de tokens**

<br/>

<a href="https://github.com/Secret-Store/backend"><img src="https://img.shields.io/badge/API%20Backend-Go%201.22+-7C3AED?style=for-the-badge&logo=go&logoColor=white" alt="Backend" /></a>
<img src="https://img.shields.io/badge/Status-Revisão%20Técnica-22D3EE?style=for-the-badge" alt="Status" />
<img src="https://img.shields.io/badge/License-All%20Rights%20Reserved-ef4444?style=for-the-badge" alt="License" />
<img src="https://img.shields.io/badge/Plataforma-SaaS-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="SaaS" />

<br/><br/>

</div>

---

## ✨ Sobre

A **Secret Store** é uma plataforma SaaS para comercialização de bots Discord em dois modelos de negócio:

| | Modelo | Como funciona |
|---|---|---|
| 🛒 | **Venda sob demanda** | Orçamento técnico → entrega → licenciamento (trial / lifetime / enterprise) → suporte |
| 🔁 | **Aluguel por assinatura** | Assina plano → entitlements → cria bot → instância em runtime → módulos ativos → bot online |

A arquitetura foi desenhada para ser **modular**, **multi-tenant**, **segura** e **orientada a eventos** — permitindo escalar bots, clientes, planos e um marketplace de módulos sem acoplamento desnecessário.

---

## 🧠 Conceito principal

> **Bot lógico não é instância de execução, e token não é configuração.**

| Conceito | Significado |
|---|---|
| 🤖 **Bot** | Produto lógico com módulos, templates e configuração-base. |
| ⚙️ **Instância** | Execução física conectada ao Discord por um *worker*. |
| 🔑 **Token** | Credencial sensível cifrada (AES-256-GCM via Vault/KMS), nunca logada. |
| 🧩 **Módulo** | Pacote plugável de comandos/eventos descrito por manifesto. |
| 🎟️ **Entitlement** | Direito concreto concedido por plano, licença ou add-on. |

---

## 🏗️ Visão da Plataforma

```text
Secret Store
│
├── 🛰️  API Backend
│   ├── Multi-Tenancy (RLS) + RBAC granular (Casbin)
│   ├── Bot · Instance · Module Services
│   ├── Plan · Entitlement · Billing · Subscription
│   ├── Quote · License
│   ├── Configuration · Feature Flags
│   └── Audit · Analytics · Notification
│
└── ⚙️  Runtime Distribuído
    ├── Runtime Manager (scheduler · sharding · failover)
    ├── Runtime Workers (N) — Plugin Engine + Discord Gateway
    └── Hot-reload · Lock distribuído (Redis)
```

---

## 🧰 Stack

| Categoria | Tecnologias |
|---|---|
| **Linguagem** | `Go 1.22+` · `discordgo` |
| **API** | REST (Chi/Fiber) · gRPC · WebSocket · CloudEvents |
| **Dados** | PostgreSQL 16 + RLS · Redis 7 · TimescaleDB · Object Storage |
| **Mensageria** | RabbitMQ · Kafka |
| **Segurança** | JWT · OAuth2 Discord · 2FA · AES-256-GCM · Vault/KMS · argon2id · mTLS |
| **Infra** | Docker · Kubernetes + Helm · Terraform · GitHub Actions |
| **Observabilidade** | Prometheus · Grafana · Jaeger · Loki · Sentry |

---

## 🛡️ Segurança crítica

- 🔒 **Tokens** cifrados com **AES-256-GCM** via Vault/KMS — o banco guarda apenas `token_ref`.
- 🧪 **Plugin Sandbox** com timeout, *panic recovery*, *rate-limit* e *resource guard*.
- 🏢 **Isolamento multi-tenant** com `tenant_id` + RLS PostgreSQL em todas as camadas.
- 📋 **Auditoria imutável** (append-only) de toda operação sensível.
- 🔐 **RBAC granular** por `recurso.acao`, *tenant-aware*.

---

## 📊 SLA Targets

| Métrica | Target |
|---|---|
| Latência API (P95) | `< 200ms` |
| Latência de comando do bot | `< 300ms` |
| Disponibilidade da plataforma | `99.9%` |
| Uptime das instâncias | `99.5%+` |
| RTO / RPO | `< 1h` / `< 15min` |

---

## 🗺️ Status & Roadmap

| Área | Status |
|---|---|
| Documentação técnica v2.0.0 | ✅ Aprovada |
| Repositório backend | ✅ Criado |
| Fundação multi-tenant + Auth + RBAC | 🧱 Planejado |
| Plugin Engine + Runtime distribuído | 🧩 Planejado |
| Billing / Entitlements / Subscription | 💳 Planejado |
| Marketplace de módulos | 🛒 Planejado |

> Roadmap completo em 5 fases (~22 semanas) disponível na documentação técnica do backend.

---

## 📚 Repositórios

| Repositório | Descrição | Stack |
|---|---|---|
| [`backend`](https://github.com/Secret-Store/backend) | API Backend da plataforma Secret Store — multi-tenant, modular e orientada a eventos. | Go · PostgreSQL · Redis · K8s |

---

## 👥 Responsáveis

| Função | Responsável |
|---|---|
| Owner / Product Owner | **Andrey V** |

---

<div align="center">

**🔐 Secret Store** — *Bots Discord modulares, seguros e escaláveis.*

© 2025 Secret Store — Todos os direitos reservados

</div>
