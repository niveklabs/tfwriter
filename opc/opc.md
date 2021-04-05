---
layout: resource
title: opc
type: provider
resource: opc
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "opc" {
  version = "1.4.1"

  # endpoint - (optional) is a type of string
  endpoint = null
  # identity_domain - (required) is a type of string
  identity_domain = null
  # insecure - (optional) is a type of bool
  insecure = null
  # lbaas_endpoint - (optional) is a type of string
  lbaas_endpoint = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # password - (required) is a type of string
  password = null
  # storage_endpoint - (optional) is a type of string
  storage_endpoint = null
  # storage_service_id - (optional) is a type of string
  storage_service_id = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Resources


- [opc_compute_acl](./r/opc_compute_acl.md)

- [opc_compute_image_list](./r/opc_compute_image_list.md)

- [opc_compute_image_list_entry](./r/opc_compute_image_list_entry.md)

- [opc_compute_instance](./r/opc_compute_instance.md)

- [opc_compute_ip_address_association](./r/opc_compute_ip_address_association.md)

- [opc_compute_ip_address_prefix_set](./r/opc_compute_ip_address_prefix_set.md)

- [opc_compute_ip_address_reservation](./r/opc_compute_ip_address_reservation.md)

- [opc_compute_ip_association](./r/opc_compute_ip_association.md)

- [opc_compute_ip_network](./r/opc_compute_ip_network.md)

- [opc_compute_ip_network_exchange](./r/opc_compute_ip_network_exchange.md)

- [opc_compute_ip_reservation](./r/opc_compute_ip_reservation.md)

- [opc_compute_machine_image](./r/opc_compute_machine_image.md)

- [opc_compute_orchestrated_instance](./r/opc_compute_orchestrated_instance.md)

- [opc_compute_route](./r/opc_compute_route.md)

- [opc_compute_sec_rule](./r/opc_compute_sec_rule.md)

- [opc_compute_security_application](./r/opc_compute_security_application.md)

- [opc_compute_security_association](./r/opc_compute_security_association.md)

- [opc_compute_security_ip_list](./r/opc_compute_security_ip_list.md)

- [opc_compute_security_list](./r/opc_compute_security_list.md)

- [opc_compute_security_protocol](./r/opc_compute_security_protocol.md)

- [opc_compute_security_rule](./r/opc_compute_security_rule.md)

- [opc_compute_snapshot](./r/opc_compute_snapshot.md)

- [opc_compute_ssh_key](./r/opc_compute_ssh_key.md)

- [opc_compute_storage_attachment](./r/opc_compute_storage_attachment.md)

- [opc_compute_storage_volume](./r/opc_compute_storage_volume.md)

- [opc_compute_storage_volume_snapshot](./r/opc_compute_storage_volume_snapshot.md)

- [opc_compute_vnic_set](./r/opc_compute_vnic_set.md)

- [opc_compute_vpn_endpoint_v2](./r/opc_compute_vpn_endpoint_v2.md)

- [opc_lbaas_certificate](./r/opc_lbaas_certificate.md)

- [opc_lbaas_listener](./r/opc_lbaas_listener.md)

- [opc_lbaas_load_balancer](./r/opc_lbaas_load_balancer.md)

- [opc_lbaas_policy](./r/opc_lbaas_policy.md)

- [opc_lbaas_server_pool](./r/opc_lbaas_server_pool.md)

- [opc_storage_container](./r/opc_storage_container.md)

- [opc_storage_object](./r/opc_storage_object.md)


[top](#index)

### Datasources


- [opc_compute_image_list_entry](./d/opc_compute_image_list_entry.md)

- [opc_compute_ip_address_reservation](./d/opc_compute_ip_address_reservation.md)

- [opc_compute_ip_reservation](./d/opc_compute_ip_reservation.md)

- [opc_compute_machine_image](./d/opc_compute_machine_image.md)

- [opc_compute_network_interface](./d/opc_compute_network_interface.md)

- [opc_compute_ssh_key](./d/opc_compute_ssh_key.md)

- [opc_compute_storage_volume_snapshot](./d/opc_compute_storage_volume_snapshot.md)

- [opc_compute_vnic](./d/opc_compute_vnic.md)


[top](#index)