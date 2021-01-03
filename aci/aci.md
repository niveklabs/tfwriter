# aci

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "aci" {
  version = "0.5.3"

  # cert_name - (optional) is a type of string
  cert_name = null
  # insecure - (optional) is a type of bool
  insecure = null
  # password - (optional) is a type of string
  password = null
  # private_key - (optional) is a type of string
  private_key = null
  # proxy_url - (optional) is a type of string
  proxy_url = null
  # url - (required) is a type of string
  url = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [aci_aaa_domain](./r/aci_aaa_domain.md)

- [aci_access_generic](./r/aci_access_generic.md)

- [aci_access_group](./r/aci_access_group.md)

- [aci_access_port_block](./r/aci_access_port_block.md)

- [aci_access_port_selector](./r/aci_access_port_selector.md)

- [aci_access_sub_port_block](./r/aci_access_sub_port_block.md)

- [aci_action_rule_profile](./r/aci_action_rule_profile.md)

- [aci_any](./r/aci_any.md)

- [aci_application_epg](./r/aci_application_epg.md)

- [aci_application_profile](./r/aci_application_profile.md)

- [aci_attachable_access_entity_profile](./r/aci_attachable_access_entity_profile.md)

- [aci_autonomous_system_profile](./r/aci_autonomous_system_profile.md)

- [aci_bridge_domain](./r/aci_bridge_domain.md)

- [aci_cdp_interface_policy](./r/aci_cdp_interface_policy.md)

- [aci_cloud_applicationcontainer](./r/aci_cloud_applicationcontainer.md)

- [aci_cloud_availability_zone](./r/aci_cloud_availability_zone.md)

- [aci_cloud_aws_provider](./r/aci_cloud_aws_provider.md)

- [aci_cloud_cidr_pool](./r/aci_cloud_cidr_pool.md)

- [aci_cloud_context_profile](./r/aci_cloud_context_profile.md)

- [aci_cloud_domain_profile](./r/aci_cloud_domain_profile.md)

- [aci_cloud_endpoint_selector](./r/aci_cloud_endpoint_selector.md)

- [aci_cloud_endpoint_selectorfor_external_epgs](./r/aci_cloud_endpoint_selectorfor_external_epgs.md)

- [aci_cloud_epg](./r/aci_cloud_epg.md)

- [aci_cloud_external_epg](./r/aci_cloud_external_epg.md)

- [aci_cloud_provider_profile](./r/aci_cloud_provider_profile.md)

- [aci_cloud_providers_region](./r/aci_cloud_providers_region.md)

- [aci_cloud_subnet](./r/aci_cloud_subnet.md)

- [aci_configuration_export_policy](./r/aci_configuration_export_policy.md)

- [aci_configuration_import_policy](./r/aci_configuration_import_policy.md)

- [aci_contract](./r/aci_contract.md)

- [aci_contract_subject](./r/aci_contract_subject.md)

- [aci_destination_of_redirected_traffic](./r/aci_destination_of_redirected_traffic.md)

- [aci_end_point_retention_policy](./r/aci_end_point_retention_policy.md)

- [aci_epg_to_contract](./r/aci_epg_to_contract.md)

- [aci_epg_to_domain](./r/aci_epg_to_domain.md)

- [aci_epg_to_static_path](./r/aci_epg_to_static_path.md)

- [aci_epgs_using_function](./r/aci_epgs_using_function.md)

- [aci_external_network_instance_profile](./r/aci_external_network_instance_profile.md)

- [aci_fabric_if_pol](./r/aci_fabric_if_pol.md)

- [aci_fabric_node_member](./r/aci_fabric_node_member.md)

- [aci_fc_domain](./r/aci_fc_domain.md)

- [aci_fex_bundle_group](./r/aci_fex_bundle_group.md)

- [aci_fex_profile](./r/aci_fex_profile.md)

- [aci_filter](./r/aci_filter.md)

- [aci_filter_entry](./r/aci_filter_entry.md)

- [aci_firmware_download_task](./r/aci_firmware_download_task.md)

- [aci_firmware_group](./r/aci_firmware_group.md)

- [aci_firmware_policy](./r/aci_firmware_policy.md)

- [aci_imported_contract](./r/aci_imported_contract.md)

- [aci_interface_fc_policy](./r/aci_interface_fc_policy.md)

- [aci_l2_interface_policy](./r/aci_l2_interface_policy.md)

- [aci_l3_domain_profile](./r/aci_l3_domain_profile.md)

- [aci_l3_ext_subnet](./r/aci_l3_ext_subnet.md)

- [aci_l3_outside](./r/aci_l3_outside.md)

- [aci_lacp_policy](./r/aci_lacp_policy.md)

- [aci_leaf_access_bundle_policy_group](./r/aci_leaf_access_bundle_policy_group.md)

- [aci_leaf_access_port_policy_group](./r/aci_leaf_access_port_policy_group.md)

- [aci_leaf_interface_profile](./r/aci_leaf_interface_profile.md)

- [aci_leaf_profile](./r/aci_leaf_profile.md)

- [aci_leaf_selector](./r/aci_leaf_selector.md)

- [aci_lldp_interface_policy](./r/aci_lldp_interface_policy.md)

- [aci_local_user](./r/aci_local_user.md)

- [aci_logical_interface_profile](./r/aci_logical_interface_profile.md)

- [aci_logical_node_profile](./r/aci_logical_node_profile.md)

- [aci_logical_node_to_fabric_node](./r/aci_logical_node_to_fabric_node.md)

- [aci_maintenance_policy](./r/aci_maintenance_policy.md)

- [aci_miscabling_protocol_interface_policy](./r/aci_miscabling_protocol_interface_policy.md)

- [aci_monitoring_policy](./r/aci_monitoring_policy.md)

- [aci_node_block](./r/aci_node_block.md)

- [aci_node_block_firmware](./r/aci_node_block_firmware.md)

- [aci_node_block_maintgrp](./r/aci_node_block_maintgrp.md)

- [aci_ospf_interface_policy](./r/aci_ospf_interface_policy.md)

- [aci_physical_domain](./r/aci_physical_domain.md)

- [aci_pod_maintenance_group](./r/aci_pod_maintenance_group.md)

- [aci_port_security_policy](./r/aci_port_security_policy.md)

- [aci_ranges](./r/aci_ranges.md)

- [aci_rest](./r/aci_rest.md)

- [aci_service_redirect_policy](./r/aci_service_redirect_policy.md)

- [aci_span_destination_group](./r/aci_span_destination_group.md)

- [aci_span_source_group](./r/aci_span_source_group.md)

- [aci_span_sourcedestination_group_match_label](./r/aci_span_sourcedestination_group_match_label.md)

- [aci_spine_interface_profile](./r/aci_spine_interface_profile.md)

- [aci_spine_port_policy_group](./r/aci_spine_port_policy_group.md)

- [aci_spine_port_selector](./r/aci_spine_port_selector.md)

- [aci_spine_profile](./r/aci_spine_profile.md)

- [aci_spine_switch_association](./r/aci_spine_switch_association.md)

- [aci_subnet](./r/aci_subnet.md)

- [aci_taboo_contract](./r/aci_taboo_contract.md)

- [aci_tenant](./r/aci_tenant.md)

- [aci_trigger_scheduler](./r/aci_trigger_scheduler.md)

- [aci_vlan_encapsulationfor_vxlan_traffic](./r/aci_vlan_encapsulationfor_vxlan_traffic.md)

- [aci_vlan_pool](./r/aci_vlan_pool.md)

- [aci_vmm_domain](./r/aci_vmm_domain.md)

- [aci_vpc_explicit_protection_group](./r/aci_vpc_explicit_protection_group.md)

- [aci_vrf](./r/aci_vrf.md)

- [aci_vsan_pool](./r/aci_vsan_pool.md)

- [aci_vxlan_pool](./r/aci_vxlan_pool.md)

- [aci_x509_certificate](./r/aci_x509_certificate.md)


[top](#index)

### Datasources


- [aci_aaa_domain](./d/aci_aaa_domain.md)

- [aci_access_generic](./d/aci_access_generic.md)

- [aci_access_group](./d/aci_access_group.md)

- [aci_access_port_block](./d/aci_access_port_block.md)

- [aci_access_port_selector](./d/aci_access_port_selector.md)

- [aci_access_sub_port_block](./d/aci_access_sub_port_block.md)

- [aci_action_rule_profile](./d/aci_action_rule_profile.md)

- [aci_any](./d/aci_any.md)

- [aci_application_epg](./d/aci_application_epg.md)

- [aci_application_profile](./d/aci_application_profile.md)

- [aci_attachable_access_entity_profile](./d/aci_attachable_access_entity_profile.md)

- [aci_autonomous_system_profile](./d/aci_autonomous_system_profile.md)

- [aci_bridge_domain](./d/aci_bridge_domain.md)

- [aci_cdp_interface_policy](./d/aci_cdp_interface_policy.md)

- [aci_client_end_point](./d/aci_client_end_point.md)

- [aci_cloud_applicationcontainer](./d/aci_cloud_applicationcontainer.md)

- [aci_cloud_availability_zone](./d/aci_cloud_availability_zone.md)

- [aci_cloud_aws_provider](./d/aci_cloud_aws_provider.md)

- [aci_cloud_cidr_pool](./d/aci_cloud_cidr_pool.md)

- [aci_cloud_context_profile](./d/aci_cloud_context_profile.md)

- [aci_cloud_domain_profile](./d/aci_cloud_domain_profile.md)

- [aci_cloud_endpoint_selector](./d/aci_cloud_endpoint_selector.md)

- [aci_cloud_endpoint_selectorfor_external_epgs](./d/aci_cloud_endpoint_selectorfor_external_epgs.md)

- [aci_cloud_epg](./d/aci_cloud_epg.md)

- [aci_cloud_external_epg](./d/aci_cloud_external_epg.md)

- [aci_cloud_provider_profile](./d/aci_cloud_provider_profile.md)

- [aci_cloud_providers_region](./d/aci_cloud_providers_region.md)

- [aci_cloud_subnet](./d/aci_cloud_subnet.md)

- [aci_configuration_export_policy](./d/aci_configuration_export_policy.md)

- [aci_configuration_import_policy](./d/aci_configuration_import_policy.md)

- [aci_contract](./d/aci_contract.md)

- [aci_contract_subject](./d/aci_contract_subject.md)

- [aci_destination_of_redirected_traffic](./d/aci_destination_of_redirected_traffic.md)

- [aci_end_point_retention_policy](./d/aci_end_point_retention_policy.md)

- [aci_epg_to_contract](./d/aci_epg_to_contract.md)

- [aci_epg_to_domain](./d/aci_epg_to_domain.md)

- [aci_epg_to_static_path](./d/aci_epg_to_static_path.md)

- [aci_epgs_using_function](./d/aci_epgs_using_function.md)

- [aci_external_network_instance_profile](./d/aci_external_network_instance_profile.md)

- [aci_fabric_if_pol](./d/aci_fabric_if_pol.md)

- [aci_fabric_node_member](./d/aci_fabric_node_member.md)

- [aci_fabric_path_ep](./d/aci_fabric_path_ep.md)

- [aci_fc_domain](./d/aci_fc_domain.md)

- [aci_fex_bundle_group](./d/aci_fex_bundle_group.md)

- [aci_fex_profile](./d/aci_fex_profile.md)

- [aci_filter](./d/aci_filter.md)

- [aci_filter_entry](./d/aci_filter_entry.md)

- [aci_firmware_download_task](./d/aci_firmware_download_task.md)

- [aci_firmware_group](./d/aci_firmware_group.md)

- [aci_firmware_policy](./d/aci_firmware_policy.md)

- [aci_imported_contract](./d/aci_imported_contract.md)

- [aci_interface_fc_policy](./d/aci_interface_fc_policy.md)

- [aci_l2_interface_policy](./d/aci_l2_interface_policy.md)

- [aci_l3_domain_profile](./d/aci_l3_domain_profile.md)

- [aci_l3_ext_subnet](./d/aci_l3_ext_subnet.md)

- [aci_l3_outside](./d/aci_l3_outside.md)

- [aci_lacp_policy](./d/aci_lacp_policy.md)

- [aci_leaf_access_bundle_policy_group](./d/aci_leaf_access_bundle_policy_group.md)

- [aci_leaf_access_port_policy_group](./d/aci_leaf_access_port_policy_group.md)

- [aci_leaf_interface_profile](./d/aci_leaf_interface_profile.md)

- [aci_leaf_profile](./d/aci_leaf_profile.md)

- [aci_leaf_selector](./d/aci_leaf_selector.md)

- [aci_lldp_interface_policy](./d/aci_lldp_interface_policy.md)

- [aci_local_user](./d/aci_local_user.md)

- [aci_logical_interface_profile](./d/aci_logical_interface_profile.md)

- [aci_logical_node_profile](./d/aci_logical_node_profile.md)

- [aci_logical_node_to_fabric_node](./d/aci_logical_node_to_fabric_node.md)

- [aci_maintenance_policy](./d/aci_maintenance_policy.md)

- [aci_miscabling_protocol_interface_policy](./d/aci_miscabling_protocol_interface_policy.md)

- [aci_monitoring_policy](./d/aci_monitoring_policy.md)

- [aci_node_block](./d/aci_node_block.md)

- [aci_node_block_firmware](./d/aci_node_block_firmware.md)

- [aci_node_block_maintgrp](./d/aci_node_block_maintgrp.md)

- [aci_ospf_interface_policy](./d/aci_ospf_interface_policy.md)

- [aci_physical_domain](./d/aci_physical_domain.md)

- [aci_pod_maintenance_group](./d/aci_pod_maintenance_group.md)

- [aci_port_security_policy](./d/aci_port_security_policy.md)

- [aci_ranges](./d/aci_ranges.md)

- [aci_service_redirect_policy](./d/aci_service_redirect_policy.md)

- [aci_span_destination_group](./d/aci_span_destination_group.md)

- [aci_span_source_group](./d/aci_span_source_group.md)

- [aci_span_sourcedestination_group_match_label](./d/aci_span_sourcedestination_group_match_label.md)

- [aci_spine_interface_profile](./d/aci_spine_interface_profile.md)

- [aci_spine_port_policy_group](./d/aci_spine_port_policy_group.md)

- [aci_spine_port_selector](./d/aci_spine_port_selector.md)

- [aci_spine_profile](./d/aci_spine_profile.md)

- [aci_spine_switch_association](./d/aci_spine_switch_association.md)

- [aci_subnet](./d/aci_subnet.md)

- [aci_taboo_contract](./d/aci_taboo_contract.md)

- [aci_tenant](./d/aci_tenant.md)

- [aci_trigger_scheduler](./d/aci_trigger_scheduler.md)

- [aci_vlan_encapsulationfor_vxlan_traffic](./d/aci_vlan_encapsulationfor_vxlan_traffic.md)

- [aci_vlan_pool](./d/aci_vlan_pool.md)

- [aci_vmm_domain](./d/aci_vmm_domain.md)

- [aci_vpc_explicit_protection_group](./d/aci_vpc_explicit_protection_group.md)

- [aci_vrf](./d/aci_vrf.md)

- [aci_vsan_pool](./d/aci_vsan_pool.md)

- [aci_vxlan_pool](./d/aci_vxlan_pool.md)

- [aci_x509_certificate](./d/aci_x509_certificate.md)


[top](#index)