# equinix

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "equinix" {
  version = "1.1.0-beta"

  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # request_timeout - (optional) is a type of number
  request_timeout = null
  # response_max_page_size - (optional) is a type of number
  response_max_page_size = null
}
```

[top](#index)

### Resources


- [equinix_ecx_l2_connection](./r/equinix_ecx_l2_connection.md)

- [equinix_ecx_l2_connection_accepter](./r/equinix_ecx_l2_connection_accepter.md)

- [equinix_ecx_l2_serviceprofile](./r/equinix_ecx_l2_serviceprofile.md)

- [equinix_network_acl_template](./r/equinix_network_acl_template.md)

- [equinix_network_bgp](./r/equinix_network_bgp.md)

- [equinix_network_device](./r/equinix_network_device.md)

- [equinix_network_ssh_key](./r/equinix_network_ssh_key.md)

- [equinix_network_ssh_user](./r/equinix_network_ssh_user.md)


[top](#index)

### Datasources


- [equinix_ecx_l2_sellerprofile](./d/equinix_ecx_l2_sellerprofile.md)

- [equinix_ecx_l2_sellerprofiles](./d/equinix_ecx_l2_sellerprofiles.md)

- [equinix_ecx_port](./d/equinix_ecx_port.md)

- [equinix_network_account](./d/equinix_network_account.md)

- [equinix_network_device_platform](./d/equinix_network_device_platform.md)

- [equinix_network_device_software](./d/equinix_network_device_software.md)

- [equinix_network_device_type](./d/equinix_network_device_type.md)


[top](#index)