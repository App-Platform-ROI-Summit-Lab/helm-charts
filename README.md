# Helm Charts

Helm charts for the **LB2863: Unlocking OpenShift's Full Value** Summit 2026 lab environment.

## Structure

### `cluster/`

Charts that configure shared cluster infrastructure. Deployed once via an ArgoCD app-of-apps pattern when the cluster is provisioned. Includes operators (Pipelines, DevSpaces, AMQ Streams), supporting services (GitLab, Vault, Quay, SonarQube), and their dependencies.

### `tenant/`

Charts that provision per-user resources on-demand. When a user requests access to the lab, the tenant bootstrap chart creates their namespaces, GitLab account, forked repositories, CI/CD pipelines, and ArgoCD applications — all scoped to their isolated environment.
