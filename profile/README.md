<div align="center">

# 🔐 Secret Store

### Plataforma modular para venda e aluguel de bots Discord

**Bots configuráveis · Multi-tenant · Marketplace de módulos · Runtime distribuído · Segurança crítica de tokens**

[![Backend](https://img.shields.io/badge/API%20Backend-Private-7C3AED?style=for-the-badge)](https://github.com/Secret-Store/backend)
[![Go](https://img.shields.io/badge/Go-1.22+-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://go.dev/)
[![Discord](https://img.shields.io/badge/Discord-Bots-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/developers/docs/intro)

</div>

---

## ✨ Sobre

A **Secret Store** é uma plataforma SaaS para comercialização de bots Discord em dois modelos:

- 🛒 **Venda sob demanda** — orçamento técnico, entrega, licenciamento e suporte.
- 🔁 **Aluguel por assinatura** — planos, módulos, entitlements, tokens e instâncias em runtime distribuído.

A arquitetura foi desenhada para ser **modular**, **multi-tenant**, **segura** e **orientada a eventos**, permitindo escalar bots, clientes, planos e marketplace sem acoplamento desnecessário.

---

## 🧠 Conceito principal

> **Bot lógico não é instância de execução, e token não é configuração.**

| Conceito | Significado |
|---|---|
| 🤖 **Bot** | Produto lógico com módulos, templates e configuração-base. |
| ⚙️ **Instância** | Execução física conectada ao Discord por um worker. |
| 🔑 **Token** | Credencial sensível armazenada em Vault/KMS e nunca logada. |
| 🧩 **Módulo** | Pacote plugável de comandos/eventos descrito por manifesto. |
| 🎟️ **Entitlement** | Direito concreto concedido por plano, licença ou add-on. |

---

## 🏗️ Plataforma

```text
Secret Store
├── API Backend
│   ├── Multi-Tenancy + RBAC
│   ├── Bot / Instance / Module Services
│   ├── Plan / Entitlement / Billing
│   ├── Quote / License
│   └── Audit / Analytics / Config
│
└── Runtime
    ├── Runtime Manager
    ├── Runtime Workers
    └── Plugin Engine
```

---

## 🚀 Status

| Área | Status |
|---|---|
| Documentação técnica v2.0.0 | ✅ Aprovada |
| Repositório backend | ✅ Criado |
| Fundação multi-tenant | 🧱 Planejado |
| Plugin Engine | 🧩 Planejado |
| Billing/Entitlements | 💳 Planejado |
| Marketplace | 🛒 Planejado |

---

## 📚 Repositórios

| Repositório | Descrição | Visibilidade |
|---|---|---|
| [`backend`](https://github.com/Secret-Store/backend) | API Backend da plataforma Secret Store. | Privado |

---

<div align="center">

**Secret Store** — Bots Discord modulares, seguros e escaláveis.

</div>
