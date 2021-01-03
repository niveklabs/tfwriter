# nutanix

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "nutanix" {
  version = "1.1.0"

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


- [nutanix_category_key](./r/nutanix_category_key.md)

- [nutanix_category_value](./r/nutanix_category_value.md)

- [nutanix_image](./r/nutanix_image.md)

- [nutanix_network_security_rule](./r/nutanix_network_security_rule.md)

- [nutanix_subnet](./r/nutanix_subnet.md)

- [nutanix_virtual_machine](./r/nutanix_virtual_machine.md)


[top](#index)

### Datasources


- [nutanix_category_key](./d/nutanix_category_key.md)

- [nutanix_cluster](./d/nutanix_cluster.md)

- [nutanix_clusters](./d/nutanix_clusters.md)

- [nutanix_host](./d/nutanix_host.md)

- [nutanix_hosts](./d/nutanix_hosts.md)

- [nutanix_image](./d/nutanix_image.md)

- [nutanix_network_security_rule](./d/nutanix_network_security_rule.md)

- [nutanix_subnet](./d/nutanix_subnet.md)

- [nutanix_subnets](./d/nutanix_subnets.md)

- [nutanix_virtual_machine](./d/nutanix_virtual_machine.md)


[top](#index)