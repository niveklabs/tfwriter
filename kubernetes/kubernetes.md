# kubernetes

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "kubernetes" {
  version = "2.0.3"

  # client_certificate - (optional) is a type of string
  client_certificate = null
  # client_key - (optional) is a type of string
  client_key = null
  # cluster_ca_certificate - (optional) is a type of string
  cluster_ca_certificate = null
  # config_context - (optional) is a type of string
  config_context = null
  # config_context_auth_info - (optional) is a type of string
  config_context_auth_info = null
  # config_context_cluster - (optional) is a type of string
  config_context_cluster = null
  # config_path - (optional) is a type of string
  config_path = null
  # config_paths - (optional) is a type of list of string
  config_paths = []
  # host - (optional) is a type of string
  host = null
  # insecure - (optional) is a type of bool
  insecure = null
  # password - (optional) is a type of string
  password = null
  # token - (optional) is a type of string
  token = null
  # username - (optional) is a type of string
  username = null

  # NestingList
  exec {
    # api_version - (required) is a type of string
    api_version = null
    # args - (optional) is a type of list of string
    args = []
    # command - (required) is a type of string
    command = null
    # env - (optional) is a type of map of string
    env = {}
  }
}
```

[top](#index)

### Resources


- [kubernetes_api_service](./r/kubernetes_api_service.md)

- [kubernetes_certificate_signing_request](./r/kubernetes_certificate_signing_request.md)

- [kubernetes_cluster_role](./r/kubernetes_cluster_role.md)

- [kubernetes_cluster_role_binding](./r/kubernetes_cluster_role_binding.md)

- [kubernetes_config_map](./r/kubernetes_config_map.md)

- [kubernetes_cron_job](./r/kubernetes_cron_job.md)

- [kubernetes_csi_driver](./r/kubernetes_csi_driver.md)

- [kubernetes_daemonset](./r/kubernetes_daemonset.md)

- [kubernetes_default_service_account](./r/kubernetes_default_service_account.md)

- [kubernetes_deployment](./r/kubernetes_deployment.md)

- [kubernetes_endpoints](./r/kubernetes_endpoints.md)

- [kubernetes_horizontal_pod_autoscaler](./r/kubernetes_horizontal_pod_autoscaler.md)

- [kubernetes_ingress](./r/kubernetes_ingress.md)

- [kubernetes_job](./r/kubernetes_job.md)

- [kubernetes_limit_range](./r/kubernetes_limit_range.md)

- [kubernetes_mutating_webhook_configuration](./r/kubernetes_mutating_webhook_configuration.md)

- [kubernetes_namespace](./r/kubernetes_namespace.md)

- [kubernetes_network_policy](./r/kubernetes_network_policy.md)

- [kubernetes_persistent_volume](./r/kubernetes_persistent_volume.md)

- [kubernetes_persistent_volume_claim](./r/kubernetes_persistent_volume_claim.md)

- [kubernetes_pod](./r/kubernetes_pod.md)

- [kubernetes_pod_disruption_budget](./r/kubernetes_pod_disruption_budget.md)

- [kubernetes_pod_security_policy](./r/kubernetes_pod_security_policy.md)

- [kubernetes_priority_class](./r/kubernetes_priority_class.md)

- [kubernetes_replication_controller](./r/kubernetes_replication_controller.md)

- [kubernetes_resource_quota](./r/kubernetes_resource_quota.md)

- [kubernetes_role](./r/kubernetes_role.md)

- [kubernetes_role_binding](./r/kubernetes_role_binding.md)

- [kubernetes_secret](./r/kubernetes_secret.md)

- [kubernetes_service](./r/kubernetes_service.md)

- [kubernetes_service_account](./r/kubernetes_service_account.md)

- [kubernetes_stateful_set](./r/kubernetes_stateful_set.md)

- [kubernetes_storage_class](./r/kubernetes_storage_class.md)

- [kubernetes_validating_webhook_configuration](./r/kubernetes_validating_webhook_configuration.md)


[top](#index)

### Datasources


- [kubernetes_all_namespaces](./d/kubernetes_all_namespaces.md)

- [kubernetes_config_map](./d/kubernetes_config_map.md)

- [kubernetes_ingress](./d/kubernetes_ingress.md)

- [kubernetes_namespace](./d/kubernetes_namespace.md)

- [kubernetes_persistent_volume_claim](./d/kubernetes_persistent_volume_claim.md)

- [kubernetes_pod](./d/kubernetes_pod.md)

- [kubernetes_secret](./d/kubernetes_secret.md)

- [kubernetes_service](./d/kubernetes_service.md)

- [kubernetes_service_account](./d/kubernetes_service_account.md)

- [kubernetes_storage_class](./d/kubernetes_storage_class.md)


[top](#index)