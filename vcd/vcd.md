---
layout: resource
title: vcd
type: provider
resource: vcd
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vcd" {
  version = "3.2.0"

  # allow_unverified_ssl - (optional) is a type of bool
  allow_unverified_ssl = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # import_separator - (optional) is a type of string
  import_separator = null
  # logging - (optional) is a type of bool
  logging = null
  # logging_file - (optional) is a type of string
  logging_file = null
  # max_retry_timeout - (optional) is a type of number
  max_retry_timeout = null
  # org - (required) is a type of string
  org = null
  # password - (optional) is a type of string
  password = null
  # saml_adfs_rpt_id - (optional) is a type of string
  saml_adfs_rpt_id = null
  # sysorg - (optional) is a type of string
  sysorg = null
  # token - (optional) is a type of string
  token = null
  # url - (required) is a type of string
  url = null
  # user - (optional) is a type of string
  user = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Resources


- [vcd_catalog](./r/vcd_catalog.md)

- [vcd_catalog_item](./r/vcd_catalog_item.md)

- [vcd_catalog_media](./r/vcd_catalog_media.md)

- [vcd_edgegateway](./r/vcd_edgegateway.md)

- [vcd_edgegateway_settings](./r/vcd_edgegateway_settings.md)

- [vcd_edgegateway_vpn](./r/vcd_edgegateway_vpn.md)

- [vcd_external_network](./r/vcd_external_network.md)

- [vcd_external_network_v2](./r/vcd_external_network_v2.md)

- [vcd_independent_disk](./r/vcd_independent_disk.md)

- [vcd_inserted_media](./r/vcd_inserted_media.md)

- [vcd_lb_app_profile](./r/vcd_lb_app_profile.md)

- [vcd_lb_app_rule](./r/vcd_lb_app_rule.md)

- [vcd_lb_server_pool](./r/vcd_lb_server_pool.md)

- [vcd_lb_service_monitor](./r/vcd_lb_service_monitor.md)

- [vcd_lb_virtual_server](./r/vcd_lb_virtual_server.md)

- [vcd_network_direct](./r/vcd_network_direct.md)

- [vcd_network_isolated](./r/vcd_network_isolated.md)

- [vcd_network_isolated_v2](./r/vcd_network_isolated_v2.md)

- [vcd_network_routed](./r/vcd_network_routed.md)

- [vcd_network_routed_v2](./r/vcd_network_routed_v2.md)

- [vcd_nsxt_edgegateway](./r/vcd_nsxt_edgegateway.md)

- [vcd_nsxt_network_dhcp](./r/vcd_nsxt_network_dhcp.md)

- [vcd_nsxt_network_imported](./r/vcd_nsxt_network_imported.md)

- [vcd_nsxv_dhcp_relay](./r/vcd_nsxv_dhcp_relay.md)

- [vcd_nsxv_dnat](./r/vcd_nsxv_dnat.md)

- [vcd_nsxv_firewall_rule](./r/vcd_nsxv_firewall_rule.md)

- [vcd_nsxv_ip_set](./r/vcd_nsxv_ip_set.md)

- [vcd_nsxv_snat](./r/vcd_nsxv_snat.md)

- [vcd_org](./r/vcd_org.md)

- [vcd_org_group](./r/vcd_org_group.md)

- [vcd_org_user](./r/vcd_org_user.md)

- [vcd_org_vdc](./r/vcd_org_vdc.md)

- [vcd_vapp](./r/vcd_vapp.md)

- [vcd_vapp_access_control](./r/vcd_vapp_access_control.md)

- [vcd_vapp_firewall_rules](./r/vcd_vapp_firewall_rules.md)

- [vcd_vapp_nat_rules](./r/vcd_vapp_nat_rules.md)

- [vcd_vapp_network](./r/vcd_vapp_network.md)

- [vcd_vapp_org_network](./r/vcd_vapp_org_network.md)

- [vcd_vapp_static_routing](./r/vcd_vapp_static_routing.md)

- [vcd_vapp_vm](./r/vcd_vapp_vm.md)

- [vcd_vm](./r/vcd_vm.md)

- [vcd_vm_affinity_rule](./r/vcd_vm_affinity_rule.md)

- [vcd_vm_internal_disk](./r/vcd_vm_internal_disk.md)

- [vcd_vm_sizing_policy](./r/vcd_vm_sizing_policy.md)


[top](#index)

### Datasources


- [vcd_catalog](./d/vcd_catalog.md)

- [vcd_catalog_item](./d/vcd_catalog_item.md)

- [vcd_catalog_media](./d/vcd_catalog_media.md)

- [vcd_edgegateway](./d/vcd_edgegateway.md)

- [vcd_external_network](./d/vcd_external_network.md)

- [vcd_external_network_v2](./d/vcd_external_network_v2.md)

- [vcd_independent_disk](./d/vcd_independent_disk.md)

- [vcd_lb_app_profile](./d/vcd_lb_app_profile.md)

- [vcd_lb_app_rule](./d/vcd_lb_app_rule.md)

- [vcd_lb_server_pool](./d/vcd_lb_server_pool.md)

- [vcd_lb_service_monitor](./d/vcd_lb_service_monitor.md)

- [vcd_lb_virtual_server](./d/vcd_lb_virtual_server.md)

- [vcd_network_direct](./d/vcd_network_direct.md)

- [vcd_network_isolated](./d/vcd_network_isolated.md)

- [vcd_network_isolated_v2](./d/vcd_network_isolated_v2.md)

- [vcd_network_routed](./d/vcd_network_routed.md)

- [vcd_network_routed_v2](./d/vcd_network_routed_v2.md)

- [vcd_nsxt_edge_cluster](./d/vcd_nsxt_edge_cluster.md)

- [vcd_nsxt_edgegateway](./d/vcd_nsxt_edgegateway.md)

- [vcd_nsxt_manager](./d/vcd_nsxt_manager.md)

- [vcd_nsxt_network_dhcp](./d/vcd_nsxt_network_dhcp.md)

- [vcd_nsxt_network_imported](./d/vcd_nsxt_network_imported.md)

- [vcd_nsxt_tier0_router](./d/vcd_nsxt_tier0_router.md)

- [vcd_nsxv_dhcp_relay](./d/vcd_nsxv_dhcp_relay.md)

- [vcd_nsxv_dnat](./d/vcd_nsxv_dnat.md)

- [vcd_nsxv_firewall_rule](./d/vcd_nsxv_firewall_rule.md)

- [vcd_nsxv_ip_set](./d/vcd_nsxv_ip_set.md)

- [vcd_nsxv_snat](./d/vcd_nsxv_snat.md)

- [vcd_org](./d/vcd_org.md)

- [vcd_org_user](./d/vcd_org_user.md)

- [vcd_org_vdc](./d/vcd_org_vdc.md)

- [vcd_portgroup](./d/vcd_portgroup.md)

- [vcd_resource_list](./d/vcd_resource_list.md)

- [vcd_resource_schema](./d/vcd_resource_schema.md)

- [vcd_storage_profile](./d/vcd_storage_profile.md)

- [vcd_vapp](./d/vcd_vapp.md)

- [vcd_vapp_network](./d/vcd_vapp_network.md)

- [vcd_vapp_org_network](./d/vcd_vapp_org_network.md)

- [vcd_vapp_vm](./d/vcd_vapp_vm.md)

- [vcd_vcenter](./d/vcd_vcenter.md)

- [vcd_vm](./d/vcd_vm.md)

- [vcd_vm_affinity_rule](./d/vcd_vm_affinity_rule.md)

- [vcd_vm_sizing_policy](./d/vcd_vm_sizing_policy.md)


[top](#index)