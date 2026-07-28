# Guía de contribución — Lukiar

Bienvenido/a al ecosistema Lukiar. Este documento es la **inducción rápida** de proceso para quien contribuye en los repositorios de la organización `lukiar-com`.

> Los repos de producto son **privados**. El detalle de stack, arquitectura y arranque local vive en la documentación interna de cada repo / workspace. Aquí solo fijamos gobernanza compartida.

---

## Principios

1. **Calidad sobre velocidad ciega** — un PR pequeño y revisable vale más que un megadiff.
2. **Un ticket, un objetivo** — no mezclar features no pedidas ni refactors colaterales.
3. **Repo correcto** — versiona el cambio en el repositorio dueño del componente.
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
fix: corregir validación de sesión en checkout
chore: actualizar dependencias de lint
```

Scope opcional: `feat(pos): …`, `fix(api): …`.

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

## Entorno de desarrollo

El onboarding técnico (herramientas, bootstrap, migraciones y comandos de desarrollo) está documentado **dentro de los repositorios privados** a los que tengas acceso.

Si eres parte del equipo y aún no tienes acceso al workspace o a un repo concreto, escríbenos a [admin@lukiar.com](mailto:admin@lukiar.com).

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
