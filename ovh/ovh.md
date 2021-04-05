---
layout: resource
title: ovh
type: provider
resource: ovh
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "ovh" {
  version = "0.11.0"

  # application_key - (optional) is a type of string
  application_key = null
  # application_secret - (optional) is a type of string
  application_secret = null
  # consumer_key - (optional) is a type of string
  consumer_key = null
  # endpoint - (required) is a type of string
  endpoint = null
}
```

[top](#index)

### Resources


- [ovh_cloud_network_private](./r/ovh_cloud_network_private.md)

- [ovh_cloud_network_private_subnet](./r/ovh_cloud_network_private_subnet.md)

- [ovh_cloud_project_kube](./r/ovh_cloud_project_kube.md)

- [ovh_cloud_project_kube_nodepool](./r/ovh_cloud_project_kube_nodepool.md)

- [ovh_cloud_project_network_private](./r/ovh_cloud_project_network_private.md)

- [ovh_cloud_project_network_private_subnet](./r/ovh_cloud_project_network_private_subnet.md)

- [ovh_cloud_project_user](./r/ovh_cloud_project_user.md)

- [ovh_cloud_user](./r/ovh_cloud_user.md)

- [ovh_dedicated_ceph_acl](./r/ovh_dedicated_ceph_acl.md)

- [ovh_dedicated_server_install_task](./r/ovh_dedicated_server_install_task.md)

- [ovh_dedicated_server_reboot_task](./r/ovh_dedicated_server_reboot_task.md)

- [ovh_dedicated_server_update](./r/ovh_dedicated_server_update.md)

- [ovh_domain_zone_record](./r/ovh_domain_zone_record.md)

- [ovh_domain_zone_redirection](./r/ovh_domain_zone_redirection.md)

- [ovh_ip_reverse](./r/ovh_ip_reverse.md)

- [ovh_iploadbalancing_http_farm](./r/ovh_iploadbalancing_http_farm.md)

- [ovh_iploadbalancing_http_farm_server](./r/ovh_iploadbalancing_http_farm_server.md)

- [ovh_iploadbalancing_http_frontend](./r/ovh_iploadbalancing_http_frontend.md)

- [ovh_iploadbalancing_http_route](./r/ovh_iploadbalancing_http_route.md)

- [ovh_iploadbalancing_http_route_rule](./r/ovh_iploadbalancing_http_route_rule.md)

- [ovh_iploadbalancing_refresh](./r/ovh_iploadbalancing_refresh.md)

- [ovh_iploadbalancing_tcp_farm](./r/ovh_iploadbalancing_tcp_farm.md)

- [ovh_iploadbalancing_tcp_farm_server](./r/ovh_iploadbalancing_tcp_farm_server.md)

- [ovh_iploadbalancing_tcp_frontend](./r/ovh_iploadbalancing_tcp_frontend.md)

- [ovh_iploadbalancing_vrack_network](./r/ovh_iploadbalancing_vrack_network.md)

- [ovh_me_identity_user](./r/ovh_me_identity_user.md)

- [ovh_me_installation_template](./r/ovh_me_installation_template.md)

- [ovh_me_installation_template_partition_scheme](./r/ovh_me_installation_template_partition_scheme.md)

- [ovh_me_installation_template_partition_scheme_hardware_raid](./r/ovh_me_installation_template_partition_scheme_hardware_raid.md)

- [ovh_me_installation_template_partition_scheme_partition](./r/ovh_me_installation_template_partition_scheme_partition.md)

- [ovh_me_ipxe_script](./r/ovh_me_ipxe_script.md)

- [ovh_me_ssh_key](./r/ovh_me_ssh_key.md)

- [ovh_vrack_cloudproject](./r/ovh_vrack_cloudproject.md)

- [ovh_vrack_dedicated_server](./r/ovh_vrack_dedicated_server.md)

- [ovh_vrack_dedicated_server_interface](./r/ovh_vrack_dedicated_server_interface.md)

- [ovh_vrack_iploadbalancing](./r/ovh_vrack_iploadbalancing.md)


[top](#index)

### Datasources


- [ovh_cloud_project_kube](./d/ovh_cloud_project_kube.md)

- [ovh_cloud_project_region](./d/ovh_cloud_project_region.md)

- [ovh_cloud_project_regions](./d/ovh_cloud_project_regions.md)

- [ovh_cloud_region](./d/ovh_cloud_region.md)

- [ovh_cloud_regions](./d/ovh_cloud_regions.md)

- [ovh_dedicated_ceph](./d/ovh_dedicated_ceph.md)

- [ovh_dedicated_installation_templates](./d/ovh_dedicated_installation_templates.md)

- [ovh_dedicated_server](./d/ovh_dedicated_server.md)

- [ovh_dedicated_server_boots](./d/ovh_dedicated_server_boots.md)

- [ovh_dedicated_servers](./d/ovh_dedicated_servers.md)

- [ovh_domain_zone](./d/ovh_domain_zone.md)

- [ovh_iploadbalancing](./d/ovh_iploadbalancing.md)

- [ovh_iploadbalancing_vrack_network](./d/ovh_iploadbalancing_vrack_network.md)

- [ovh_iploadbalancing_vrack_networks](./d/ovh_iploadbalancing_vrack_networks.md)

- [ovh_me_identity_user](./d/ovh_me_identity_user.md)

- [ovh_me_identity_users](./d/ovh_me_identity_users.md)

- [ovh_me_installation_template](./d/ovh_me_installation_template.md)

- [ovh_me_installation_templates](./d/ovh_me_installation_templates.md)

- [ovh_me_ipxe_script](./d/ovh_me_ipxe_script.md)

- [ovh_me_ipxe_scripts](./d/ovh_me_ipxe_scripts.md)

- [ovh_me_paymentmean_bankaccount](./d/ovh_me_paymentmean_bankaccount.md)

- [ovh_me_paymentmean_creditcard](./d/ovh_me_paymentmean_creditcard.md)

- [ovh_me_ssh_key](./d/ovh_me_ssh_key.md)

- [ovh_me_ssh_keys](./d/ovh_me_ssh_keys.md)

- [ovh_vps](./d/ovh_vps.md)

- [ovh_vracks](./d/ovh_vracks.md)


[top](#index)