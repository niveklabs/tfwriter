---
layout: resource
title: triton
type: provider
resource: triton
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "triton" {
  version = "0.8.1"

  # account - (optional) is a type of string
  account = null
  # insecure_skip_tls_verify - (optional) is a type of bool
  insecure_skip_tls_verify = null
  # key_id - (optional) is a type of string
  key_id = null
  # key_material - (optional) is a type of string
  key_material = null
  # url - (optional) is a type of string
  url = null
  # user - (optional) is a type of string
  user = null
}
```

[top](#index)

### Resources


- [triton_fabric](./r/triton_fabric.md)

- [triton_firewall_rule](./r/triton_firewall_rule.md)

- [triton_instance_template](./r/triton_instance_template.md)

- [triton_key](./r/triton_key.md)

- [triton_machine](./r/triton_machine.md)

- [triton_service_group](./r/triton_service_group.md)

- [triton_snapshot](./r/triton_snapshot.md)

- [triton_vlan](./r/triton_vlan.md)

- [triton_volume](./r/triton_volume.md)


[top](#index)

### Datasources


- [triton_account](./d/triton_account.md)

- [triton_datacenter](./d/triton_datacenter.md)

- [triton_fabric_network](./d/triton_fabric_network.md)

- [triton_fabric_vlan](./d/triton_fabric_vlan.md)

- [triton_image](./d/triton_image.md)

- [triton_network](./d/triton_network.md)

- [triton_package](./d/triton_package.md)

- [triton_volume](./d/triton_volume.md)


[top](#index)