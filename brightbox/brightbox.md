# brightbox

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "brightbox" {
  version = "1.5.0"

  # account - (optional) is a type of string
  account = null
  # apiclient - (optional) is a type of string
  apiclient = null
  # apisecret - (optional) is a type of string
  apisecret = null
  # apiurl - (optional) is a type of string
  apiurl = null
  # orbit_url - (optional) is a type of string
  orbit_url = null
  # password - (optional) is a type of string
  password = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [brightbox_api_client](./r/brightbox_api_client.md)

- [brightbox_cloudip](./r/brightbox_cloudip.md)

- [brightbox_config_map](./r/brightbox_config_map.md)

- [brightbox_database_server](./r/brightbox_database_server.md)

- [brightbox_firewall_policy](./r/brightbox_firewall_policy.md)

- [brightbox_firewall_rule](./r/brightbox_firewall_rule.md)

- [brightbox_load_balancer](./r/brightbox_load_balancer.md)

- [brightbox_orbit_container](./r/brightbox_orbit_container.md)

- [brightbox_server](./r/brightbox_server.md)

- [brightbox_server_group](./r/brightbox_server_group.md)


[top](#index)

### Datasources


- [brightbox_database_type](./d/brightbox_database_type.md)

- [brightbox_image](./d/brightbox_image.md)

- [brightbox_server_group](./d/brightbox_server_group.md)


[top](#index)