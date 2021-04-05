---
layout: resource
title: scaleway
type: provider
resource: scaleway
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "scaleway" {
  version = "2.0.0"

  # access_key - (optional) is a type of string
  access_key = null
  # api_url - (optional) is a type of string
  api_url = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Resources


- [scaleway_account_ssh_key](./r/scaleway_account_ssh_key.md)

- [scaleway_apple_silicon_server](./r/scaleway_apple_silicon_server.md)

- [scaleway_baremetal_server](./r/scaleway_baremetal_server.md)

- [scaleway_instance_ip](./r/scaleway_instance_ip.md)

- [scaleway_instance_ip_reverse_dns](./r/scaleway_instance_ip_reverse_dns.md)

- [scaleway_instance_placement_group](./r/scaleway_instance_placement_group.md)

- [scaleway_instance_private_nic](./r/scaleway_instance_private_nic.md)

- [scaleway_instance_security_group](./r/scaleway_instance_security_group.md)

- [scaleway_instance_security_group_rules](./r/scaleway_instance_security_group_rules.md)

- [scaleway_instance_server](./r/scaleway_instance_server.md)

- [scaleway_instance_volume](./r/scaleway_instance_volume.md)

- [scaleway_iot_device](./r/scaleway_iot_device.md)

- [scaleway_iot_hub](./r/scaleway_iot_hub.md)

- [scaleway_iot_network](./r/scaleway_iot_network.md)

- [scaleway_iot_route](./r/scaleway_iot_route.md)

- [scaleway_k8s_cluster](./r/scaleway_k8s_cluster.md)

- [scaleway_k8s_pool](./r/scaleway_k8s_pool.md)

- [scaleway_lb](./r/scaleway_lb.md)

- [scaleway_lb_backend](./r/scaleway_lb_backend.md)

- [scaleway_lb_certificate](./r/scaleway_lb_certificate.md)

- [scaleway_lb_frontend](./r/scaleway_lb_frontend.md)

- [scaleway_lb_ip](./r/scaleway_lb_ip.md)

- [scaleway_object_bucket](./r/scaleway_object_bucket.md)

- [scaleway_rdb_instance](./r/scaleway_rdb_instance.md)

- [scaleway_rdb_user](./r/scaleway_rdb_user.md)

- [scaleway_registry_namespace](./r/scaleway_registry_namespace.md)

- [scaleway_vpc_private_network](./r/scaleway_vpc_private_network.md)


[top](#index)

### Datasources


- [scaleway_account_ssh_key](./d/scaleway_account_ssh_key.md)

- [scaleway_baremetal_offer](./d/scaleway_baremetal_offer.md)

- [scaleway_instance_image](./d/scaleway_instance_image.md)

- [scaleway_instance_security_group](./d/scaleway_instance_security_group.md)

- [scaleway_instance_server](./d/scaleway_instance_server.md)

- [scaleway_instance_volume](./d/scaleway_instance_volume.md)

- [scaleway_k8s_cluster](./d/scaleway_k8s_cluster.md)

- [scaleway_k8s_pool](./d/scaleway_k8s_pool.md)

- [scaleway_lb_ip](./d/scaleway_lb_ip.md)

- [scaleway_marketplace_image](./d/scaleway_marketplace_image.md)

- [scaleway_rdb_instance](./d/scaleway_rdb_instance.md)

- [scaleway_registry_image](./d/scaleway_registry_image.md)

- [scaleway_registry_namespace](./d/scaleway_registry_namespace.md)

- [scaleway_vpc_private_network](./d/scaleway_vpc_private_network.md)


[top](#index)