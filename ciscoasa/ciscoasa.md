# ciscoasa

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "ciscoasa" {
  version = "1.2.0"

  # api_url - (required) is a type of string
  api_url = null
  # password - (required) is a type of string
  password = null
  # ssl_no_verify - (optional) is a type of bool
  ssl_no_verify = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [ciscoasa_access_in_rules](./r/ciscoasa_access_in_rules.md)

- [ciscoasa_access_out_rules](./r/ciscoasa_access_out_rules.md)

- [ciscoasa_acl](./r/ciscoasa_acl.md)

- [ciscoasa_network_object](./r/ciscoasa_network_object.md)

- [ciscoasa_network_object_group](./r/ciscoasa_network_object_group.md)

- [ciscoasa_network_service_group](./r/ciscoasa_network_service_group.md)

- [ciscoasa_static_route](./r/ciscoasa_static_route.md)


[top](#index)

### Datasources



[top](#index)