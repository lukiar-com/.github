# Política de seguridad

En Lukiar tomamos en serio la seguridad de nuestros sistemas, datos de negocios y de consumidores. Agradecemos los reportes responsables de vulnerabilidades.

---

## Divulgación responsable

Si descubres una vulnerabilidad de seguridad (en APIs, autenticación/OIDC, aislamiento multitenant, almacenamiento de media, frontends, infra o dependencias), **no** abras un issue público ni un PR que la exponga.

### Cómo reportar

Envía un correo a:

**[admin@lukiar.com](mailto:admin@lukiar.com)**

Asunto sugerido: `[SECURITY] Descripción breve`

Incluye, en la medida de lo posible:

- Descripción clara del problema y su impacto potencial
- Pasos reproducibles o PoC mínima (sin datos reales de clientes)
- Componente afectado (repo, servicio, endpoint, versión aproximada)
- Tu evaluación de severidad (baja / media / alta / crítica)
- Cómo contactarte para seguimiento

---

## Tiempos de respuesta

| Etapa | Objetivo |
| ----- | -------- |
| Acuse de recibo | **48–72 horas** hábiles |
| Evaluación inicial y clasificación | Hasta **7 días** tras el acuse |
| Plan de remediación o mitigación | Según severidad; se comunica al reporter |

Nos comprometemos a mantener informado al reporter sobre el estado del caso, dentro de lo razonable y sin comprometer investigaciones en curso.

---

## Alcance

**Dentro de alcance (ejemplos):**

- Escalada de privilegios o bypass de autenticación/autorización
- Fugas de datos entre tenants (aislamiento multitenant)
- Inyección, XSS, CSRF, SSRF u otros defectos explotables en producción
- Exposición indebida de secretos, tokens o PII
- Misconfiguración de storage/CDN que permita acceso no autorizado a objetos privados

**Fuera de alcance (ejemplos):**

- Denegación de servicio volumétrica sin vector de abuso de aplicación
- Reportes de versiones desactualizadas sin exploit demostrable
- Hallazgos solo en entornos locales de desarrollo sin impacto en prod
- Ingeniería social dirigida a usuarios finales o al equipo

---

## Buenas prácticas para investigadores

- No accedas, modifiques ni destruyas datos que no sean tuyos
- No ejecutes escaneos agresivos contra producción sin coordinación previa
- No publiques detalles hasta que confirmemos una remediación o ventana acordada
- Si el hallazgo involucra un tercero (proveedor cloud, dependencia), indícalo para coordinar divulgación

---

## Agradecimientos

Valoramos el trabajo ético de la comunidad de seguridad. Cuando corresponda, reconocemos a los reporters que colaboran de forma responsable (salvo que pidan anonimato).

Gracias por ayudar a proteger a los negocios y personas que confían en Lukiar.

— Equipo de Ingeniería Lukiar  
[admin@lukiar.com](mailto:admin@lukiar.com) · [https://lukiar.com](https://lukiar.com)
