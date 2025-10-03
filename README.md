[![CI: compose-validate](https://img.shields.io/github/actions/workflow/status/mariano-tp/github-observability-demo/compose-validate.yml?branch=main&label=compose-validate&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/actions/workflows/compose-validate.yml)
[![CI: link-check](https://img.shields.io/github/actions/workflow/status/mariano-tp/github-observability-demo/link-check.yml?branch=main&label=link-check&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/actions/workflows/link-check.yml)
[![last commit](https://img.shields.io/github/last-commit/mariano-tp/github-observability-demo?style=flat-square)](https://github.com/mariano-tp/github-observability-demo/commits/main)
[![release](https://img.shields.io/github/v/release/mariano-tp/github-observability-demo?display_name=tag&style=flat-square)](https://github.com/mariano-tp/github-observability-demo/releases)
[![license: MIT](https://img.shields.io/badge/license-MIT-green?style=flat-square)](./LICENSE)
[![stars](https://img.shields.io/github/stars/mariano-tp/github-observability-demo?style=flat-square)](https://github.com/mariano-tp/github-observability-demo/stargazers)


# GitHub Observability Demo

Observability demo for **GitHub metrics** using **Prometheus + Grafana + github-exporter**.  
Designed to showcase **observability practices** and **CI in GitHub Actions**, without needing to install anything locally.

> Based on community work (github-monitoring). This fork is used for educational purposes.

## What’s included?
- **Prometheus** scrapes metrics from the GitHub exporter.
- **Grafana** with a dashboard for statistics (stars, forks, issues) of sample repos.
- **CI**: workflow `compose-validate` validates `docker-compose.yml` on each push/PR.

## Structure
```
.
├─ grafana/          # dashboards and provisioning
├─ prometheus/       # Prometheus configuration
├─ images/           # screenshots used in this README
├─ docker-compose.yml
└─ config.monitoring # example variables (REPOS, etc.)
```

## How it runs (optional)
Running locally is not required to review the code or CI.  
If someone wants to execute it locally with Docker Compose:

1. Create a **GitHub Personal Access Token** (PAT) with `public_repo` scope (or `repo` if private).
2. Define environment variables:
   - `REPOS` (comma-separated, e.g. `freeCodeCamp/freeCodeCamp,docker/docker`)
   - `GITHUB_TOKEN` (your PAT)
3. Launch:
```bash
docker compose up -d
```

- Grafana: `http://localhost:3000` (user `admin`, password defined in `config.monitoring`)  
- Prometheus: `http://localhost:9090`

## Screenshots
**Dashboard**  
![Dashboard](images/dashboard.png)

**GitHub Token (PAT)**  
![PAT](images/github_token.png)

**Datasource in Grafana**  
![Datasource](images/Grafana_Add_Data_Source.png)

**Import dashboard**  
![Import](images/Import_Dashboard.png)

## CI (GitHub Actions)
This repository automatically runs:
- `docker compose -f docker-compose.yml config` → validates syntax and references.

## Credits
Original stack from the community (github-monitoring) + presentation and CI adjustments by @mariano-tp.

See also: [Code of Conduct](./CODE_OF_CONDUCT.md) · [Contributing](./CONTRIBUTING.md) · [Security](./SECURITY.md)
