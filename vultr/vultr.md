---
layout: resource
title: vultr
type: provider
resource: vultr
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vultr" {
  version = "2.2.0"

  # api_key - (required) is a type of string
  api_key = null
  # rate_limit - (optional) is a type of number
  rate_limit = null
  # retry_limit - (optional) is a type of number
  retry_limit = null
}
```

[top](#index)

### Resources


- [vultr_bare_metal_server](./r/vultr_bare_metal_server.md)

- [vultr_block_storage](./r/vultr_block_storage.md)

- [vultr_dns_domain](./r/vultr_dns_domain.md)

- [vultr_dns_record](./r/vultr_dns_record.md)

- [vultr_firewall_group](./r/vultr_firewall_group.md)

- [vultr_firewall_rule](./r/vultr_firewall_rule.md)

- [vultr_instance](./r/vultr_instance.md)

- [vultr_instance_ipv4](./r/vultr_instance_ipv4.md)

- [vultr_iso_private](./r/vultr_iso_private.md)

- [vultr_load_balancer](./r/vultr_load_balancer.md)

- [vultr_object_storage](./r/vultr_object_storage.md)

- [vultr_private_network](./r/vultr_private_network.md)

- [vultr_reserved_ip](./r/vultr_reserved_ip.md)

- [vultr_reverse_ipv4](./r/vultr_reverse_ipv4.md)

- [vultr_reverse_ipv6](./r/vultr_reverse_ipv6.md)

- [vultr_snapshot](./r/vultr_snapshot.md)

- [vultr_snapshot_from_url](./r/vultr_snapshot_from_url.md)

- [vultr_ssh_key](./r/vultr_ssh_key.md)

- [vultr_startup_script](./r/vultr_startup_script.md)

- [vultr_user](./r/vultr_user.md)


[top](#index)

### Datasources


- [vultr_account](./d/vultr_account.md)

- [vultr_application](./d/vultr_application.md)

- [vultr_backup](./d/vultr_backup.md)

- [vultr_bare_metal_plan](./d/vultr_bare_metal_plan.md)

- [vultr_bare_metal_server](./d/vultr_bare_metal_server.md)

- [vultr_block_storage](./d/vultr_block_storage.md)

- [vultr_dns_domain](./d/vultr_dns_domain.md)

- [vultr_firewall_group](./d/vultr_firewall_group.md)

- [vultr_instance](./d/vultr_instance.md)

- [vultr_instance_ipv4](./d/vultr_instance_ipv4.md)

- [vultr_iso_private](./d/vultr_iso_private.md)

- [vultr_iso_public](./d/vultr_iso_public.md)

- [vultr_load_balancer](./d/vultr_load_balancer.md)

- [vultr_object_storage](./d/vultr_object_storage.md)

- [vultr_os](./d/vultr_os.md)

- [vultr_plan](./d/vultr_plan.md)

- [vultr_private_network](./d/vultr_private_network.md)

- [vultr_region](./d/vultr_region.md)

- [vultr_reserved_ip](./d/vultr_reserved_ip.md)

- [vultr_reverse_ipv4](./d/vultr_reverse_ipv4.md)

- [vultr_reverse_ipv6](./d/vultr_reverse_ipv6.md)

- [vultr_snapshot](./d/vultr_snapshot.md)

- [vultr_ssh_key](./d/vultr_ssh_key.md)

- [vultr_startup_script](./d/vultr_startup_script.md)

- [vultr_user](./d/vultr_user.md)


[top](#index)