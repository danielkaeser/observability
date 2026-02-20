# Monitoring stack (production-leaning) via Helmfile

This bundle installs kube-prometheus-stack plus optional "friends":
- Prometheus Adapter (HPA custom/external metrics)
- Blackbox Exporter
- Loki + Promtail (logs)
- Tempo (traces)
- (Optional) Thanos is stubbed (commented) for later

## Quick start
```bash
cd monitoring-prod
helmfile repos
helmfile -e prod apply
```

## Customize
1. Edit `environments/prod.yaml` for your cluster specifics:
   - storageClassName
   - ingress class
   - hostnames
2. Put secrets in your preferred secrets manager.
   - This repo uses placeholders + `values/secret-overrides.example.yaml`
   - Recommended: External Secrets Operator or SOPS + helmfile `secrets:`

## Notes
- Grafana admin password is **not** committed; set it via secrets.
- Ingress is configured for ingress-nginx by default and expects cert-manager ClusterIssuer.
