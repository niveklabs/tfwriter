---
layout: resource
title: nutanix
type: provider
resource: nutanix
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "nutanix" {
  version = "1.2.0"

  # endpoint - (required) is a type of string
  endpoint = null
  # insecure - (optional) is a type of bool
  insecure = null
  # password - (required) is a type of string
  password = null
  # port - (optional) is a type of string
  port = null
  # proxy_url - (optional) is a type of string
  proxy_url = null
  # session_auth - (optional) is a type of bool
  session_auth = null
  # username - (required) is a type of string
  username = null
  # wait_timeout - (optional) is a type of number
  wait_timeout = null
}
```

[top](#index)

### Resources


- [nutanix_access_control_policy](./r/nutanix_access_control_policy.md)

- [nutanix_category_key](./r/nutanix_category_key.md)

- [nutanix_category_value](./r/nutanix_category_value.md)

- [nutanix_image](./r/nutanix_image.md)

- [nutanix_karbon_cluster](./r/nutanix_karbon_cluster.md)

- [nutanix_karbon_private_registry](./r/nutanix_karbon_private_registry.md)

- [nutanix_network_security_rule](./r/nutanix_network_security_rule.md)

- [nutanix_project](./r/nutanix_project.md)

- [nutanix_protection_rule](./r/nutanix_protection_rule.md)

- [nutanix_recovery_plan](./r/nutanix_recovery_plan.md)

- [nutanix_role](./r/nutanix_role.md)

- [nutanix_subnet](./r/nutanix_subnet.md)

- [nutanix_user](./r/nutanix_user.md)

- [nutanix_virtual_machine](./r/nutanix_virtual_machine.md)


[top](#index)

### Datasources


- [nutanix_access_control_policies](./d/nutanix_access_control_policies.md)

- [nutanix_access_control_policy](./d/nutanix_access_control_policy.md)

- [nutanix_category_key](./d/nutanix_category_key.md)

- [nutanix_cluster](./d/nutanix_cluster.md)

- [nutanix_clusters](./d/nutanix_clusters.md)

- [nutanix_host](./d/nutanix_host.md)

- [nutanix_hosts](./d/nutanix_hosts.md)

- [nutanix_image](./d/nutanix_image.md)

- [nutanix_karbon_cluster](./d/nutanix_karbon_cluster.md)

- [nutanix_karbon_cluster_kubeconfig](./d/nutanix_karbon_cluster_kubeconfig.md)

- [nutanix_karbon_cluster_ssh](./d/nutanix_karbon_cluster_ssh.md)

- [nutanix_karbon_clusters](./d/nutanix_karbon_clusters.md)

- [nutanix_karbon_private_registries](./d/nutanix_karbon_private_registries.md)

- [nutanix_karbon_private_registry](./d/nutanix_karbon_private_registry.md)

- [nutanix_network_security_rule](./d/nutanix_network_security_rule.md)

- [nutanix_permission](./d/nutanix_permission.md)

- [nutanix_permissions](./d/nutanix_permissions.md)

- [nutanix_project](./d/nutanix_project.md)

- [nutanix_projects](./d/nutanix_projects.md)

- [nutanix_protection_rule](./d/nutanix_protection_rule.md)

- [nutanix_protection_rules](./d/nutanix_protection_rules.md)

- [nutanix_recovery_plan](./d/nutanix_recovery_plan.md)

- [nutanix_recovery_plans](./d/nutanix_recovery_plans.md)

- [nutanix_role](./d/nutanix_role.md)

- [nutanix_roles](./d/nutanix_roles.md)

- [nutanix_subnet](./d/nutanix_subnet.md)

- [nutanix_subnets](./d/nutanix_subnets.md)

- [nutanix_user](./d/nutanix_user.md)

- [nutanix_user_group](./d/nutanix_user_group.md)

- [nutanix_user_groups](./d/nutanix_user_groups.md)

- [nutanix_users](./d/nutanix_users.md)

- [nutanix_virtual_machine](./d/nutanix_virtual_machine.md)


[top](#index)