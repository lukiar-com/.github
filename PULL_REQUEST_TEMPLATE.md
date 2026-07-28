## Resumen

<!-- ¿Qué cambia y por qué? 2–5 oraciones. Enfócate en el impacto, no en el diff línea a línea. -->

## Ticket / issue

- Ticket: <!-- enlace a Linear / GitHub Issue / etc. -->
- Tipo: <!-- feat | fix | chore | docs | refactor -->

## Cambios principales

-
-
-

## Checklist de QA (obligatorio)

### Verificación local

- [ ] Probé el flujo afectado en local (`pnpm dev` / servicio concreto)
- [ ] No rompí contratos de API públicos ni de sync SaaS ↔ app pública (si aplica)
- [ ] Revisé migraciones / seeds / variables de entorno tocadas (si aplica)

### Calidad de código

- [ ] Lint pasa en el/los paquetes modificados (`pnpm lint` o equivalente del repo)
- [ ] Tests relevantes pasan (`pnpm test`, `cargo test`, script de integración del repo)
- [ ] Tipado / build OK (`pnpm build` / `cargo check` según stack)

### Revisión

- [ ] Diff acotado al ticket (sin refactors no solicitados)
- [ ] Commits siguen [Conventional Commits](./CONTRIBUTING.md#conventional-commits) en español
- [ ] Documentación actualizada si el cambio altera comportamiento o contratos
- [ ] Sin secretos, `.env` ni credenciales en el PR

## Plan de prueba (revisor)

1.
2.
3.

## Notas / riesgos

<!-- Breaking changes, deploy ordenado multi-repo, feature flags, rollback, etc. -->

## Capturas (si aplica UI)

<!-- Antes / después o enlace a Loom -->
