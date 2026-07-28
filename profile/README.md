# Lukiar

> Plataforma SaaS multitenant para que negocios de LatAm operen, vendan y se descubran en un solo ecosistema.

[![Web](https://img.shields.io/badge/web-lukiar.com-111827?style=flat-square)](https://lukiar.com)
[![Contacto](https://img.shields.io/badge/contacto-admin%40lukiar.com-0f766e?style=flat-square)](mailto:admin@lukiar.com)

---

## Qué es Lukiar

Lukiar ayuda a restaurantes, peluquerías, gimnasios, retail, hoteles, productoras y más a digitalizar su operación: menú QR, POS, cocina (KDS), cola de pedidos (QMS), agenda, tickets, sitio web del negocio y presencia en la app pública para consumidores.

Modelo comercial claro: **Free forever**, **Trial Pro** y **Pro** por vertical (cuota fija, 0 % comisión sobre ventas del negocio).

---

## Tech stack

Stack real del ecosistema (multi-repo privado bajo `github.com/lukiar-com`):

| Capa | Tecnologías |
| ---- | ----------- |
| **Backends** | Rust · Actix-web · SQLx · PostgreSQL / PostGIS · Valkey · REST + SSE · OIDC |
| **Frontends web** | TypeScript · React 19 · Next.js 16 (App Router) · Vite 7/8 · Tailwind CSS v4 · React Query · Headless UI |
| **Apps staff** | Dashboard, POS, KDS, QMS, Agenda, Tickets (Vite + React) |
| **Canales tenant** | Menú digital · Website / e-commerce (Next.js) |
| **Escritorio** | Tauri v2 (agente de impresión Mac + Windows) |
| **Ops / DX** | pnpm `11.5.2` · Cargo workspace · GitHub Actions · AWS (ECS, S3, CloudFront) · Vercel (landing) |

---

## Organización

Los repositorios de producto son **privados**. Este repositorio (`.github`) es el **centro de gobernanza** de la organización: perfil público, políticas de seguridad, plantillas de issues/PR y guías de contribución por defecto.

| Recurso | Enlace |
| ------- | ------ |
| Sitio | [https://lukiar.com](https://lukiar.com) |
| Contacto / seguridad | [admin@lukiar.com](mailto:admin@lukiar.com) |
| Contribuir | [CONTRIBUTING.md](../CONTRIBUTING.md) |
| Seguridad | [SECURITY.md](../SECURITY.md) |

---

<p align="center">
  <sub>Hecho con foco en operación real de negocios · Lukiar Engineering</sub>
</p>
