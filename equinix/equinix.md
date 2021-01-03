# equinix

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "equinix" {
  version = "1.0.2"

  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # request_timeout - (optional) is a type of number
  request_timeout = null
}
```

[top](#index)

### Resources


- [equinix_ecx_l2_connection](./r/equinix_ecx_l2_connection.md)

- [equinix_ecx_l2_connection_accepter](./r/equinix_ecx_l2_connection_accepter.md)

- [equinix_ecx_l2_serviceprofile](./r/equinix_ecx_l2_serviceprofile.md)


[top](#index)

### Datasources


- [equinix_ecx_l2_sellerprofile](./d/equinix_ecx_l2_sellerprofile.md)

- [equinix_ecx_port](./d/equinix_ecx_port.md)


[top](#index)