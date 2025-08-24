# Guía de Contribución

Gracias por tu interés 🙌. Este repo muestra un stack de observabilidad (Prometheus + Grafana + exporter) y CI en GitHub Actions.

## Flujo de trabajo
1. **Abrí un issue** usando la plantilla (Mejora de dashboard / Bug).
2. **Creá una rama** desde `main`:
   - `feat/<breve-descripcion>` para nuevas features
   - `fix/<breve-descripcion>` para bugs
   - `docs/...`, `ci/...` para documentación o pipelines
3. **Commits** con prefijo estilo *Conventional Commits*:
   - `feat:`, `fix:`, `docs:`, `ci:`, `chore:`
4. **Pull Request**:
   - Un solo tema por PR
   - Link al issue
   - Pasar todos los checks de CI
   - Actualizar README/capturas si aplica

## Checks de CI
- `compose-validate`: valida `docker-compose.yml`
- *(Opcional si lo ves en Actions)* `link-check`: revisa links del README

## Reporte de bugs
Incluí:
- Pasos para reproducir
- Resultado esperado vs. actual
- Logs o capturas (si aplica)

## Estilo
- Markdown simple y claro (español)
- Archivos en `images/` para capturas
- Nombres de ramas en minúsculas y con guiones

## Licencia
Al contribuir aceptás que tu aporte se publica bajo **MIT** (ver `LICENSE`).
