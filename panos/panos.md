---
layout: resource
title: panos
type: provider
resource: panos
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "panos" {
  version = "1.8.1"

  # api_key - (optional) is a type of string
  api_key = null
  # hostname - (optional) is a type of string
  hostname = null
  # json_config_file - (optional) is a type of string
  json_config_file = null
  # logging - (optional) is a type of list of string
  logging = []
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # target - (optional) is a type of string
  target = null
  # timeout - (optional) is a type of number
  timeout = null
  # username - (optional) is a type of string
  username = null
  # verify_certificate - (optional) is a type of bool
  verify_certificate = null
}
```

[top](#index)

### Resources


- [panos_address_group](./r/panos_address_group.md)

- [panos_address_object](./r/panos_address_object.md)

- [panos_administrative_tag](./r/panos_administrative_tag.md)

- [panos_aggregate_interface](./r/panos_aggregate_interface.md)

- [panos_anti_spyware_security_profile](./r/panos_anti_spyware_security_profile.md)

- [panos_antivirus_security_profile](./r/panos_antivirus_security_profile.md)

- [panos_application_group](./r/panos_application_group.md)

- [panos_application_object](./r/panos_application_object.md)

- [panos_application_signature](./r/panos_application_signature.md)

- [panos_arp](./r/panos_arp.md)

- [panos_bfd_profile](./r/panos_bfd_profile.md)

- [panos_bgp](./r/panos_bgp.md)

- [panos_bgp_aggregate](./r/panos_bgp_aggregate.md)

- [panos_bgp_aggregate_advertise_filter](./r/panos_bgp_aggregate_advertise_filter.md)

- [panos_bgp_aggregate_suppress_filter](./r/panos_bgp_aggregate_suppress_filter.md)

- [panos_bgp_auth_profile](./r/panos_bgp_auth_profile.md)

- [panos_bgp_conditional_adv](./r/panos_bgp_conditional_adv.md)

- [panos_bgp_conditional_adv_advertise_filter](./r/panos_bgp_conditional_adv_advertise_filter.md)

- [panos_bgp_conditional_adv_non_exist_filter](./r/panos_bgp_conditional_adv_non_exist_filter.md)

- [panos_bgp_dampening_profile](./r/panos_bgp_dampening_profile.md)

- [panos_bgp_export_rule_group](./r/panos_bgp_export_rule_group.md)

- [panos_bgp_import_rule_group](./r/panos_bgp_import_rule_group.md)

- [panos_bgp_peer](./r/panos_bgp_peer.md)

- [panos_bgp_peer_group](./r/panos_bgp_peer_group.md)

- [panos_bgp_redist_rule](./r/panos_bgp_redist_rule.md)

- [panos_custom_data_pattern_object](./r/panos_custom_data_pattern_object.md)

- [panos_dag_tags](./r/panos_dag_tags.md)

- [panos_data_filtering_security_profile](./r/panos_data_filtering_security_profile.md)

- [panos_device_group_parent](./r/panos_device_group_parent.md)

- [panos_dos_protection_profile](./r/panos_dos_protection_profile.md)

- [panos_dynamic_user_group](./r/panos_dynamic_user_group.md)

- [panos_edl](./r/panos_edl.md)

- [panos_email_server_profile](./r/panos_email_server_profile.md)

- [panos_ethernet_interface](./r/panos_ethernet_interface.md)

- [panos_file_blocking_security_profile](./r/panos_file_blocking_security_profile.md)

- [panos_general_settings](./r/panos_general_settings.md)

- [panos_gre_tunnel](./r/panos_gre_tunnel.md)

- [panos_http_server_profile](./r/panos_http_server_profile.md)

- [panos_ike_crypto_profile](./r/panos_ike_crypto_profile.md)

- [panos_ike_gateway](./r/panos_ike_gateway.md)

- [panos_ip_tag](./r/panos_ip_tag.md)

- [panos_ipsec_crypto_profile](./r/panos_ipsec_crypto_profile.md)

- [panos_ipsec_tunnel](./r/panos_ipsec_tunnel.md)

- [panos_ipsec_tunnel_proxy_id_ipv4](./r/panos_ipsec_tunnel_proxy_id_ipv4.md)

- [panos_layer2_subinterface](./r/panos_layer2_subinterface.md)

- [panos_layer3_subinterface](./r/panos_layer3_subinterface.md)

- [panos_license_api_key](./r/panos_license_api_key.md)

- [panos_licensing](./r/panos_licensing.md)

- [panos_log_forwarding_profile](./r/panos_log_forwarding_profile.md)

- [panos_loopback_interface](./r/panos_loopback_interface.md)

- [panos_management_profile](./r/panos_management_profile.md)

- [panos_monitor_profile](./r/panos_monitor_profile.md)

- [panos_nat_policy](./r/panos_nat_policy.md)

- [panos_nat_rule](./r/panos_nat_rule.md)

- [panos_nat_rule_group](./r/panos_nat_rule_group.md)

- [panos_ospf](./r/panos_ospf.md)

- [panos_ospf_area](./r/panos_ospf_area.md)

- [panos_ospf_area_interface](./r/panos_ospf_area_interface.md)

- [panos_ospf_area_virtual_link](./r/panos_ospf_area_virtual_link.md)

- [panos_ospf_auth_profile](./r/panos_ospf_auth_profile.md)

- [panos_ospf_export](./r/panos_ospf_export.md)

- [panos_panorama_address_group](./r/panos_panorama_address_group.md)

- [panos_panorama_address_object](./r/panos_panorama_address_object.md)

- [panos_panorama_administrative_tag](./r/panos_panorama_administrative_tag.md)

- [panos_panorama_aggregate_interface](./r/panos_panorama_aggregate_interface.md)

- [panos_panorama_application_group](./r/panos_panorama_application_group.md)

- [panos_panorama_application_object](./r/panos_panorama_application_object.md)

- [panos_panorama_application_signature](./r/panos_panorama_application_signature.md)

- [panos_panorama_bfd_profile](./r/panos_panorama_bfd_profile.md)

- [panos_panorama_bgp](./r/panos_panorama_bgp.md)

- [panos_panorama_bgp_aggregate](./r/panos_panorama_bgp_aggregate.md)

- [panos_panorama_bgp_aggregate_advertise_filter](./r/panos_panorama_bgp_aggregate_advertise_filter.md)

- [panos_panorama_bgp_aggregate_suppress_filter](./r/panos_panorama_bgp_aggregate_suppress_filter.md)

- [panos_panorama_bgp_auth_profile](./r/panos_panorama_bgp_auth_profile.md)

- [panos_panorama_bgp_conditional_adv](./r/panos_panorama_bgp_conditional_adv.md)

- [panos_panorama_bgp_conditional_adv_advertise_filter](./r/panos_panorama_bgp_conditional_adv_advertise_filter.md)

- [panos_panorama_bgp_conditional_adv_non_exist_filter](./r/panos_panorama_bgp_conditional_adv_non_exist_filter.md)

- [panos_panorama_bgp_dampening_profile](./r/panos_panorama_bgp_dampening_profile.md)

- [panos_panorama_bgp_export_rule_group](./r/panos_panorama_bgp_export_rule_group.md)

- [panos_panorama_bgp_import_rule_group](./r/panos_panorama_bgp_import_rule_group.md)

- [panos_panorama_bgp_peer](./r/panos_panorama_bgp_peer.md)

- [panos_panorama_bgp_peer_group](./r/panos_panorama_bgp_peer_group.md)

- [panos_panorama_bgp_redist_rule](./r/panos_panorama_bgp_redist_rule.md)

- [panos_panorama_device_group](./r/panos_panorama_device_group.md)

- [panos_panorama_device_group_entry](./r/panos_panorama_device_group_entry.md)

- [panos_panorama_edl](./r/panos_panorama_edl.md)

- [panos_panorama_email_server_profile](./r/panos_panorama_email_server_profile.md)

- [panos_panorama_ethernet_interface](./r/panos_panorama_ethernet_interface.md)

- [panos_panorama_gcp_account](./r/panos_panorama_gcp_account.md)

- [panos_panorama_gke_cluster](./r/panos_panorama_gke_cluster.md)

- [panos_panorama_gke_cluster_group](./r/panos_panorama_gke_cluster_group.md)

- [panos_panorama_gre_tunnel](./r/panos_panorama_gre_tunnel.md)

- [panos_panorama_http_server_profile](./r/panos_panorama_http_server_profile.md)

- [panos_panorama_ike_crypto_profile](./r/panos_panorama_ike_crypto_profile.md)

- [panos_panorama_ike_gateway](./r/panos_panorama_ike_gateway.md)

- [panos_panorama_ipsec_crypto_profile](./r/panos_panorama_ipsec_crypto_profile.md)

- [panos_panorama_ipsec_tunnel](./r/panos_panorama_ipsec_tunnel.md)

- [panos_panorama_ipsec_tunnel_proxy_id_ipv4](./r/panos_panorama_ipsec_tunnel_proxy_id_ipv4.md)

- [panos_panorama_layer2_subinterface](./r/panos_panorama_layer2_subinterface.md)

- [panos_panorama_layer3_subinterface](./r/panos_panorama_layer3_subinterface.md)

- [panos_panorama_log_forwarding_profile](./r/panos_panorama_log_forwarding_profile.md)

- [panos_panorama_loopback_interface](./r/panos_panorama_loopback_interface.md)

- [panos_panorama_management_profile](./r/panos_panorama_management_profile.md)

- [panos_panorama_monitor_profile](./r/panos_panorama_monitor_profile.md)

- [panos_panorama_nat_policy](./r/panos_panorama_nat_policy.md)

- [panos_panorama_nat_rule](./r/panos_panorama_nat_rule.md)

- [panos_panorama_nat_rule_group](./r/panos_panorama_nat_rule_group.md)

- [panos_panorama_pbf_rule_group](./r/panos_panorama_pbf_rule_group.md)

- [panos_panorama_redistribution_profile_ipv4](./r/panos_panorama_redistribution_profile_ipv4.md)

- [panos_panorama_security_policies](./r/panos_panorama_security_policies.md)

- [panos_panorama_security_policy](./r/panos_panorama_security_policy.md)

- [panos_panorama_security_policy_group](./r/panos_panorama_security_policy_group.md)

- [panos_panorama_security_rule_group](./r/panos_panorama_security_rule_group.md)

- [panos_panorama_service_group](./r/panos_panorama_service_group.md)

- [panos_panorama_service_object](./r/panos_panorama_service_object.md)

- [panos_panorama_snmptrap_server_profile](./r/panos_panorama_snmptrap_server_profile.md)

- [panos_panorama_static_route_ipv4](./r/panos_panorama_static_route_ipv4.md)

- [panos_panorama_syslog_server_profile](./r/panos_panorama_syslog_server_profile.md)

- [panos_panorama_template](./r/panos_panorama_template.md)

- [panos_panorama_template_entry](./r/panos_panorama_template_entry.md)

- [panos_panorama_template_stack](./r/panos_panorama_template_stack.md)

- [panos_panorama_template_stack_entry](./r/panos_panorama_template_stack_entry.md)

- [panos_panorama_template_variable](./r/panos_panorama_template_variable.md)

- [panos_panorama_tunnel_interface](./r/panos_panorama_tunnel_interface.md)

- [panos_panorama_virtual_router](./r/panos_panorama_virtual_router.md)

- [panos_panorama_virtual_router_entry](./r/panos_panorama_virtual_router_entry.md)

- [panos_panorama_vlan](./r/panos_panorama_vlan.md)

- [panos_panorama_vlan_entry](./r/panos_panorama_vlan_entry.md)

- [panos_panorama_vlan_interface](./r/panos_panorama_vlan_interface.md)

- [panos_panorama_zone](./r/panos_panorama_zone.md)

- [panos_panorama_zone_entry](./r/panos_panorama_zone_entry.md)

- [panos_pbf_rule_group](./r/panos_pbf_rule_group.md)

- [panos_redistribution_profile_ipv4](./r/panos_redistribution_profile_ipv4.md)

- [panos_security_policies](./r/panos_security_policies.md)

- [panos_security_policy](./r/panos_security_policy.md)

- [panos_security_policy_group](./r/panos_security_policy_group.md)

- [panos_security_rule_group](./r/panos_security_rule_group.md)

- [panos_service_group](./r/panos_service_group.md)

- [panos_service_object](./r/panos_service_object.md)

- [panos_snmptrap_server_profile](./r/panos_snmptrap_server_profile.md)

- [panos_static_route_ipv4](./r/panos_static_route_ipv4.md)

- [panos_syslog_server_profile](./r/panos_syslog_server_profile.md)

- [panos_telemetry](./r/panos_telemetry.md)

- [panos_tunnel_interface](./r/panos_tunnel_interface.md)

- [panos_url_filtering_security_profile](./r/panos_url_filtering_security_profile.md)

- [panos_user_tag](./r/panos_user_tag.md)

- [panos_userid_login](./r/panos_userid_login.md)

- [panos_virtual_router](./r/panos_virtual_router.md)

- [panos_virtual_router_entry](./r/panos_virtual_router_entry.md)

- [panos_vlan](./r/panos_vlan.md)

- [panos_vlan_entry](./r/panos_vlan_entry.md)

- [panos_vlan_interface](./r/panos_vlan_interface.md)

- [panos_vm_auth_key](./r/panos_vm_auth_key.md)

- [panos_vulnerability_security_profile](./r/panos_vulnerability_security_profile.md)

- [panos_wildfire_analysis_security_profile](./r/panos_wildfire_analysis_security_profile.md)

- [panos_zone](./r/panos_zone.md)

- [panos_zone_entry](./r/panos_zone_entry.md)


[top](#index)

### Datasources


- [panos_address_object](./d/panos_address_object.md)

- [panos_address_objects](./d/panos_address_objects.md)

- [panos_anti_spyware_security_profile](./d/panos_anti_spyware_security_profile.md)

- [panos_anti_spyware_security_profiles](./d/panos_anti_spyware_security_profiles.md)

- [panos_antivirus_security_profile](./d/panos_antivirus_security_profile.md)

- [panos_antivirus_security_profiles](./d/panos_antivirus_security_profiles.md)

- [panos_api_key](./d/panos_api_key.md)

- [panos_arp](./d/panos_arp.md)

- [panos_arps](./d/panos_arps.md)

- [panos_custom_data_pattern_object](./d/panos_custom_data_pattern_object.md)

- [panos_custom_data_pattern_objects](./d/panos_custom_data_pattern_objects.md)

- [panos_data_filtering_security_profile](./d/panos_data_filtering_security_profile.md)

- [panos_data_filtering_security_profiles](./d/panos_data_filtering_security_profiles.md)

- [panos_device_group_parent](./d/panos_device_group_parent.md)

- [panos_dhcp_interface_info](./d/panos_dhcp_interface_info.md)

- [panos_dos_protection_profile](./d/panos_dos_protection_profile.md)

- [panos_dos_protection_profiles](./d/panos_dos_protection_profiles.md)

- [panos_dynamic_user_group](./d/panos_dynamic_user_group.md)

- [panos_dynamic_user_groups](./d/panos_dynamic_user_groups.md)

- [panos_file_blocking_security_profile](./d/panos_file_blocking_security_profile.md)

- [panos_file_blocking_security_profiles](./d/panos_file_blocking_security_profiles.md)

- [panos_ip_tag](./d/panos_ip_tag.md)

- [panos_ospf](./d/panos_ospf.md)

- [panos_ospf_area](./d/panos_ospf_area.md)

- [panos_ospf_area_interface](./d/panos_ospf_area_interface.md)

- [panos_ospf_area_interfaces](./d/panos_ospf_area_interfaces.md)

- [panos_ospf_area_virtual_link](./d/panos_ospf_area_virtual_link.md)

- [panos_ospf_area_virtual_links](./d/panos_ospf_area_virtual_links.md)

- [panos_ospf_areas](./d/panos_ospf_areas.md)

- [panos_ospf_auth_profiles](./d/panos_ospf_auth_profiles.md)

- [panos_ospf_export](./d/panos_ospf_export.md)

- [panos_ospf_exports](./d/panos_ospf_exports.md)

- [panos_panorama_plugin](./d/panos_panorama_plugin.md)

- [panos_plugin](./d/panos_plugin.md)

- [panos_predefined_dlp_file_type](./d/panos_predefined_dlp_file_type.md)

- [panos_predefined_tdb_file_type](./d/panos_predefined_tdb_file_type.md)

- [panos_predefined_threat](./d/panos_predefined_threat.md)

- [panos_system_info](./d/panos_system_info.md)

- [panos_url_filtering_security_profile](./d/panos_url_filtering_security_profile.md)

- [panos_url_filtering_security_profiles](./d/panos_url_filtering_security_profiles.md)

- [panos_user_tag](./d/panos_user_tag.md)

- [panos_vm_auth_key](./d/panos_vm_auth_key.md)

- [panos_vulnerability_security_profile](./d/panos_vulnerability_security_profile.md)

- [panos_vulnerability_security_profiles](./d/panos_vulnerability_security_profiles.md)

- [panos_wildfire_analysis_security_profile](./d/panos_wildfire_analysis_security_profile.md)

- [panos_wildfire_analysis_security_profiles](./d/panos_wildfire_analysis_security_profiles.md)


[top](#index)