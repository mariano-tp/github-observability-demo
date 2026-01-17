> Available languages / Idiomas disponibles: [*English*](README.md) / [*Español*](README.ES.md)

Back to repository: [Home](https://github.com/mariano-tp/mariano-tp/blob/main/README.md)

[![CI: compose-validate](https://img.shields.io/github/actions/workflow/status/mariano-tp/github-observability-demo/compose-validate.yml?branch=main&label=compose-validate&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/actions/workflows/compose-validate.yml)
[![CI: link-check](https://img.shields.io/github/actions/workflow/status/mariano-tp/github-observability-demo/link-check.yml?branch=main&label=link-check&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/actions/workflows/link-check.yml)
[![last commit](https://img.shields.io/github/last-commit/mariano-tp/github-observability-demo?style=flat-square)](https://github.com/mariano-tp/github-observability-demo/commits/main)
[![release](https://img.shields.io/github/v/release/mariano-tp/github-observability-demo?display_name=tag&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/releases)
[![license: MIT](https://img.shields.io/badge/license-MIT-green?style=flat-square)](./LICENSE)
[![stars](https://img.shields.io/github/stars/mariano-tp/github-observability-demo?style=flat-square)](https://github.com/mariano-tp/github-observability-demo/stargazers)

# GitHub Observability Demo

Observability demo for GitHub repository metrics using Prometheus + Grafana + GitHub exporter.

Designed to showcase observability practices and CI in GitHub Actions. Reviewing the project does not require running anything locally.

This repository is based on community work (github-monitoring) and is used for educational/portfolio purposes.

## What gets validated in CI (GitHub Actions)
- compose-validate (compose-validate.yml)
  - Validates docker-compose.yml using docker compose config

- link-check (link-check.yml)
  - Validates README links (basic documentation quality gate)

Evidence: workflow logs in Actions.

## What’s included
- Prometheus scrapes metrics from the GitHub exporter
- Grafana provides dashboards for repository statistics (stars, forks, issues) for a list of sample repos
- Docker Compose stack with ready-to-use configuration

## Structure
    .
    ├─ grafana/          # Dashboards and provisioning
    ├─ prometheus/       # Prometheus configuration
    ├─ images/           # Screenshots used in this README
    ├─ docker-compose.yml
    └─ config.monitoring # Example variables (REPOS, etc.)

## Optional local run (not required for evaluation)
Running locally is not required to review the code or CI.

If you want to execute it with Docker Compose:
1. Create a GitHub Personal Access Token (PAT) with public repo access (or repo if private)
2. Define environment variables:
   - REPOS (comma-separated), e.g. freeCodeCamp/freeCodeCamp,docker/docker
   - GITHUB_TOKEN (your PAT)
3. Launch:

    docker compose up -d

Grafana: http://localhost:3000 (user admin, password defined in config.monitoring)
Prometheus: http://localhost:9090

## Screenshots
Dashboard  
![Dashboard](images/dashboard.png)

GitHub Token (PAT)  
![PAT](images/github_token.png)

Datasource in Grafana  
![Datasource](images/Grafana_Add_Data_Source.png)

Import dashboard  
![Import](images/Import_Dashboard.png)

## Credits
Original stack from the community (github-monitoring) with CI and documentation adjustments by @mariano-tp.

See also: [Code of Conduct](./CODE_OF_CONDUCT.md) · [Contributing](./CONTRIBUTING.md) · [Security](./SECURITY.md)
