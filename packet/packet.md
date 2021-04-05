---
layout: resource
title: packet
type: provider
resource: packet
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "packet" {
  version = "3.2.1"

  # auth_token - (required) is a type of string
  auth_token = null
}
```

[top](#index)

### Resources


- [packet_bgp_session](./r/packet_bgp_session.md)

- [packet_device](./r/packet_device.md)

- [packet_device_network_type](./r/packet_device_network_type.md)

- [packet_ip_attachment](./r/packet_ip_attachment.md)

- [packet_organization](./r/packet_organization.md)

- [packet_port_vlan_attachment](./r/packet_port_vlan_attachment.md)

- [packet_project](./r/packet_project.md)

- [packet_project_ssh_key](./r/packet_project_ssh_key.md)

- [packet_reserved_ip_block](./r/packet_reserved_ip_block.md)

- [packet_spot_market_request](./r/packet_spot_market_request.md)

- [packet_ssh_key](./r/packet_ssh_key.md)

- [packet_vlan](./r/packet_vlan.md)

- [packet_volume](./r/packet_volume.md)

- [packet_volume_attachment](./r/packet_volume_attachment.md)


[top](#index)

### Datasources


- [packet_device](./d/packet_device.md)

- [packet_device_bgp_neighbors](./d/packet_device_bgp_neighbors.md)

- [packet_ip_block_ranges](./d/packet_ip_block_ranges.md)

- [packet_operating_system](./d/packet_operating_system.md)

- [packet_organization](./d/packet_organization.md)

- [packet_precreated_ip_block](./d/packet_precreated_ip_block.md)

- [packet_project](./d/packet_project.md)

- [packet_project_ssh_key](./d/packet_project_ssh_key.md)

- [packet_spot_market_price](./d/packet_spot_market_price.md)

- [packet_spot_market_request](./d/packet_spot_market_request.md)

- [packet_volume](./d/packet_volume.md)


[top](#index)