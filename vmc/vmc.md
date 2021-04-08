---
layout: resource
title: vmc
type: provider
resource: vmc
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vmc" {
  version = "1.5.1"

  # csp_url - (optional) is a type of string
  csp_url = null
  # org_id - (required) is a type of string
  org_id = null
  # refresh_token - (required) is a type of string
  refresh_token = null
  # vmc_url - (optional) is a type of string
  vmc_url = null
}
```

[top](#index)

### Resources


- [vmc_cluster](./r/vmc_cluster.md)

- [vmc_public_ip](./r/vmc_public_ip.md)

- [vmc_sddc](./r/vmc_sddc.md)

- [vmc_site_recovery](./r/vmc_site_recovery.md)

- [vmc_srm_node](./r/vmc_srm_node.md)


[top](#index)

### Datasources


- [vmc_connected_accounts](./d/vmc_connected_accounts.md)

- [vmc_customer_subnets](./d/vmc_customer_subnets.md)

- [vmc_org](./d/vmc_org.md)


[top](#index)