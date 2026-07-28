# Guía de contribución — Lukiar

Bienvenido/a al ecosistema Lukiar. Este documento es la **inducción rápida** para quien contribuye en los repositorios de la organización `lukiar-com`.

> Los repos de producto son privados. Las reglas de este archivo aplican por defecto a toda la organización salvo que un repo declare lo contrario.

---

## Principios

1. **Calidad sobre velocidad ciega** — un PR pequeño y revisable vale más que un megadiff.
2. **Un ticket, un objetivo** — no mezclar features no pedidas ni refactors colaterales.
3. **Multi-repo consciente** — cada carpeta/`lukiar-*` es su propio git; versiona en el repo correcto.
4. **Idioma** — documentación, comentarios y commits en **español**; nombres de código (variables, tipos, archivos) en **inglés**.

---

## Conventional Commits

Formato: `tipo: descripción en español`

| Tipo | Uso |
| ---- | --- |
| `feat` | Nueva funcionalidad |
| `fix` | Corrección de un bug |
| `chore` | Mantenimiento (deps, config, CI) |
| `docs` | Solo documentación |
| `refactor` | Cambio interno sin alterar comportamiento externo |

Ejemplos:

```text
feat: agregar filtro por categoría en el catálogo
fix: corregir aislamiento de tenant en listado de pedidos
chore: actualizar pnpm a 11.5.2
```

Scope opcional: `feat(pos): …`, `fix(saas-backend): …`.

---

## Estrategia de ramas

Rama principal: **`main`**. Los PRs siempre apuntan a `main`.

| Prefijo | Uso |
| ------- | --- |
| `feature/<nombre-tarea>` | Nueva funcionalidad o mejora |
| `fix/<nombre-tarea>` | Corrección de bug |
| `chore/<nombre-tarea>` | Mantenimiento / tooling |
| `docs/<nombre-tarea>` | Solo docs |

```bash
git checkout main && git pull
git checkout -b feature/filtro-catalogo
# … trabajo …
git push -u origin feature/filtro-catalogo
# Abrir PR hacia main (usar plantilla de PR)
```

Reglas:

- Nombre en **kebab-case**, corto y ligado al ticket
- Evitar commits directos a `main` en modo equipo
- Si el cambio cruza varios repos, abre **un PR por repo** y coordina el orden de merge/deploy

---

## Entorno local (workspace)

El desarrollo habitual ocurre en el workspace contenedor [`lukiar-com`](https://github.com/lukiar-com/lukiar-com), que clona los subproyectos y orquesta el stack.

### Prerrequisitos

- **Node.js** 20+
- **pnpm** `11.5.2` (declarado en `packageManager`)
- **Rust** estable (edition 2021; backends Actix-web)
- **PostgreSQL** (dev local) + extensión PostGIS para la app pública
- **Valkey** o Redis compatible (caché / pub-sub SaaS)
- **Git**

### Bootstrap

```bash
# 1. Clonar el workspace
git clone https://github.com/lukiar-com/lukiar-com.git
cd lukiar-com

# 2. Clonar los subproyectos (multi-repo)
./scripts/bootstrap.sh          # HTTPS
# ./scripts/bootstrap.sh --ssh  # SSH

# 3. Dependencias del orquestador
pnpm install

# 4. En cada frontend que toques
cd lukiar-saas-dashboard && pnpm install && cd ..
# … repetir según el repo de trabajo …

# 5. Migraciones
pnpm migrate:saas
pnpm migrate:public

# 6. Levantar el ecosistema
pnpm infra          # PostgreSQL + Valkey (si aplica el script)
pnpm dev            # backends + frontends + gateway (+ print-agent)
pnpm dev:lite       # igual, sin print-agent (menos RAM)
```

Comandos útiles:

| Comando | Qué hace |
| ------- | -------- |
| `pnpm dev:back` | Solo backends Rust (`:8080`, `:8081`) |
| `pnpm dev:front` | Solo frontends |
| `pnpm stop` / `pnpm restart` | Detener / reiniciar procesos del orquestador |
| `pnpm smoke:…` | Smokes de autenticación, pedidos, L360, etc. |

Detalle de puertos y flujos: ver `GUIA-DESARROLLO.md` en el workspace.

---

## Antes de abrir un PR

1. Rama desde `main` actualizado
2. Commits con Conventional Commits
3. Lint + tests locales del repo tocado
4. Completar la [plantilla de Pull Request](./PULL_REQUEST_TEMPLATE.md)
5. Enlazar el ticket de la tarea

---

## Reportes y propuestas

- **Bugs:** plantilla [Bug report](./.github/ISSUE_TEMPLATE/bug_report.md)
- **Features:** plantilla [Feature request](./.github/ISSUE_TEMPLATE/feature_request.md)
- **Seguridad:** **no** uses issues públicos — sigue [SECURITY.md](./SECURITY.md) → `admin@lukiar.com`

---

## Código de conducta (resumen)

Trato profesional, feedback constructivo y foco en el producto. Discrepancias técnicas se resuelven con datos, no con ego.

---

## Contacto

- Ingeniería / admin: [admin@lukiar.com](mailto:admin@lukiar.com)
- Producto: [https://lukiar.com](https://lukiar.com)

¡Gracias por contribuir a Lukiar!
