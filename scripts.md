# Creating Grafana admin secret
kubectl -n monitoring create secret generic grafana-admin   --from-literal=admin-user=admin   --from-literal=admin-password='REPLACE_ME'

# Or manage it via External Secrets / SOPS.
