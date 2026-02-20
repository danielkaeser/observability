# Observability stack (production-leaning) via Helmfile

This bundle installs kube-prometheus-stack plus optional "friends":
- Prometheus Adapter (HPA custom/external metrics)
- Blackbox Exporter
- Loki + Promtail (logs)
- Tempo (traces)
- Alloy

## Quick start
```bash
helmfile -e default apply
```

## Setup

Needs a local executable file `set-env-vars.sh`

```bash
export OIDC_CLIENT_ID=<CLIENT>
export OIDC_CLIENT_SECRET=<SECRET>
export OIDC_SESSION_SECRET=<SECRET>
export OIDC_DISCOVERY_URL=https://auth.danielkaeser2026.de/realms/demo/.well-known/openid-configuration

export GRAFANA_ADMIN_PASSWORD=<SECRET>
```
