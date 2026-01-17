> Available languages / Idiomas disponibles: [*English*](README.md) / [*Español*](README.ES.md)

Back to repository: [Home](https://github.com/mariano-tp/mariano-tp/blob/main/README.ES.md)  

[![CI: compose-validate](https://img.shields.io/github/actions/workflow/status/mariano-tp/github-observability-demo/compose-validate.yml?branch=main&label=compose-validate&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/actions/workflows/compose-validate.yml)
[![CI: link-check](https://img.shields.io/github/actions/workflow/status/mariano-tp/github-observability-demo/link-check.yml?branch=main&label=link-check&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/actions/workflows/link-check.yml)
[![last commit](https://img.shields.io/github/last-commit/mariano-tp/github-observability-demo?style=flat-square)](https://github.com/mariano-tp/github-observability-demo/commits/main)
[![release](https://img.shields.io/github/v/release/mariano-tp/github-observability-demo?display_name=tag&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/releases)
[![license: MIT](https://img.shields.io/badge/license-MIT-green?style=flat-square)](./LICENSE)
[![stars](https://img.shields.io/github/stars/mariano-tp/github-observability-demo?style=flat-square)](https://github.com/mariano-tp/github-observability-demo/stargazers)

# GitHub Observability Demo

Demo de observabilidad para métricas de repositorios GitHub usando Prometheus + Grafana + un exporter para GitHub.

Está pensado para mostrar prácticas de observabilidad y validación por CI en GitHub Actions. Para revisar el proyecto no hace falta ejecutar nada en local.

Este repositorio está basado en trabajo de la comunidad (github-monitoring) y se usa con fines educativos y de portfolio.

## Qué se valida en CI (GitHub Actions)
- compose-validate (compose-validate.yml)
  - Valida docker-compose.yml usando docker compose config

- link-check (link-check.yml)
  - Revisa enlaces del README (control básico de calidad de documentación)

Evidencia: logs de los workflows en Actions.

## Qué incluye
- Prometheus scrapea métricas desde el exporter de GitHub
- Grafana ofrece dashboards con estadísticas de repositorios (stars, forks, issues) para una lista de repos de ejemplo
- Stack con Docker Compose y configuración lista para usar

## Estructura
    .
    ├─ grafana/          # Dashboards y provisioning
    ├─ prometheus/       # Configuración de Prometheus
    ├─ images/           # Capturas usadas en este README
    ├─ docker-compose.yml
    └─ config.monitoring # Variables de ejemplo (REPOS, etc.)

## Ejecución local opcional (no requerida para evaluación)
Correrlo localmente no es necesario para revisar el código o el CI.

Si querés ejecutarlo con Docker Compose:
1. Creá un GitHub Personal Access Token (PAT) con acceso a repos públicos (o repo si es privado)
2. Definí variables de entorno:
   - REPOS (separados por coma), por ejemplo freeCodeCamp/freeCodeCamp,docker/docker
   - GITHUB_TOKEN (tu PAT)
3. Levantalo con:

    docker compose up -d

Grafana: http://localhost:3000 (usuario admin, contraseña definida en config.monitoring)
Prometheus: http://localhost:9090

## Capturas
Dashboard  
![Dashboard](images/dashboard.png)

GitHub Token (PAT)  
![PAT](images/github_token.png)

Datasource en Grafana  
![Datasource](images/Grafana_Add_Data_Source.png)

Importar dashboard  
![Import](images/Import_Dashboard.png)

## Créditos
Stack original de la comunidad (github-monitoring) con ajustes de CI y documentación por @mariano-tp.

Ver también: [Code of Conduct](./CODE_OF_CONDUCT.md) · [Contributing](./CONTRIBUTING.md) · [Security](./SECURITY.md)
