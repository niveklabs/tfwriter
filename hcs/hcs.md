# hcs

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "hcs" {
  version = "0.2.0"

  # azure_client_certificate_password - (optional) is a type of string
  azure_client_certificate_password = null
  # azure_client_certificate_path - (optional) is a type of string
  azure_client_certificate_path = null
  # azure_client_id - (optional) is a type of string
  azure_client_id = null
  # azure_client_secret - (optional) is a type of string
  azure_client_secret = null
  # azure_environment - (optional) is a type of string
  azure_environment = null
  # azure_metadata_host - (optional) is a type of string
  azure_metadata_host = null
  # azure_msi_endpoint - (optional) is a type of string
  azure_msi_endpoint = null
  # azure_subscription_id - (optional) is a type of string
  azure_subscription_id = null
  # azure_tenant_id - (optional) is a type of string
  azure_tenant_id = null
  # azure_use_msi - (optional) is a type of bool
  azure_use_msi = null
  # hcp_api_domain - (optional) is a type of string
  hcp_api_domain = null
  # hcs_marketplace_product_name - (optional) is a type of string
  hcs_marketplace_product_name = null
}
```

[top](#index)

### Resources


- [hcs_cluster](./r/hcs_cluster.md)

- [hcs_cluster_root_token](./r/hcs_cluster_root_token.md)

- [hcs_snapshot](./r/hcs_snapshot.md)


[top](#index)

### Datasources


- [hcs_agent_helm_config](./d/hcs_agent_helm_config.md)

- [hcs_agent_kubernetes_secret](./d/hcs_agent_kubernetes_secret.md)

- [hcs_cluster](./d/hcs_cluster.md)

- [hcs_consul_versions](./d/hcs_consul_versions.md)

- [hcs_federation_token](./d/hcs_federation_token.md)

- [hcs_plan_defaults](./d/hcs_plan_defaults.md)


[top](#index)