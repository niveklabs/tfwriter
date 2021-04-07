---
layout: resource
title: hcp
type: provider
resource: hcp
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "hcp" {
  version = "0.4.0"

  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
}
```

[top](#index)

### Resources


- [hcp_aws_network_peering](./r/hcp_aws_network_peering.md)

- [hcp_aws_transit_gateway_attachment](./r/hcp_aws_transit_gateway_attachment.md)

- [hcp_consul_cluster](./r/hcp_consul_cluster.md)

- [hcp_consul_cluster_root_token](./r/hcp_consul_cluster_root_token.md)

- [hcp_consul_snapshot](./r/hcp_consul_snapshot.md)

- [hcp_hvn](./r/hcp_hvn.md)

- [hcp_vault_cluster](./r/hcp_vault_cluster.md)

- [hcp_vault_cluster_admin_token](./r/hcp_vault_cluster_admin_token.md)


[top](#index)

### Datasources


- [hcp_aws_network_peering](./d/hcp_aws_network_peering.md)

- [hcp_aws_transit_gateway_attachment](./d/hcp_aws_transit_gateway_attachment.md)

- [hcp_consul_agent_helm_config](./d/hcp_consul_agent_helm_config.md)

- [hcp_consul_agent_kubernetes_secret](./d/hcp_consul_agent_kubernetes_secret.md)

- [hcp_consul_cluster](./d/hcp_consul_cluster.md)

- [hcp_consul_versions](./d/hcp_consul_versions.md)

- [hcp_hvn](./d/hcp_hvn.md)

- [hcp_vault_cluster](./d/hcp_vault_cluster.md)


[top](#index)