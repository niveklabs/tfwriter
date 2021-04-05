---
layout: resource
title: nsxt
type: provider
resource: nsxt
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "nsxt" {
  version = "3.1.1"

  # allow_unverified_ssl - (optional) is a type of bool
  allow_unverified_ssl = null
  # ca - (optional) is a type of string
  ca = null
  # ca_file - (optional) is a type of string
  ca_file = null
  # client_auth_cert - (optional) is a type of string
  client_auth_cert = null
  # client_auth_cert_file - (optional) is a type of string
  client_auth_cert_file = null
  # client_auth_key - (optional) is a type of string
  client_auth_key = null
  # client_auth_key_file - (optional) is a type of string
  client_auth_key_file = null
  # enforcement_point - (optional) is a type of string
  enforcement_point = null
  # global_manager - (optional) is a type of bool
  global_manager = null
  # host - (optional) is a type of string
  host = null
  # license_keys - (optional) is a type of list of string
  license_keys = []
  # max_retries - (optional) is a type of number
  max_retries = null
  # password - (optional) is a type of string
  password = null
  # remote_auth - (optional) is a type of bool
  remote_auth = null
  # retry_max_delay - (optional) is a type of number
  retry_max_delay = null
  # retry_min_delay - (optional) is a type of number
  retry_min_delay = null
  # retry_on_status_codes - (optional) is a type of list of number
  retry_on_status_codes = []
  # tolerate_partial_success - (optional) is a type of bool
  tolerate_partial_success = null
  # username - (optional) is a type of string
  username = null
  # vmc_auth_host - (optional) is a type of string
  vmc_auth_host = null
  # vmc_auth_mode - (optional) is a type of string
  vmc_auth_mode = null
  # vmc_token - (optional) is a type of string
  vmc_token = null
}
```

[top](#index)

### Resources


- [nsxt_algorithm_type_ns_service](./r/nsxt_algorithm_type_ns_service.md)

- [nsxt_dhcp_relay_profile](./r/nsxt_dhcp_relay_profile.md)

- [nsxt_dhcp_relay_service](./r/nsxt_dhcp_relay_service.md)

- [nsxt_dhcp_server_ip_pool](./r/nsxt_dhcp_server_ip_pool.md)

- [nsxt_dhcp_server_profile](./r/nsxt_dhcp_server_profile.md)

- [nsxt_ether_type_ns_service](./r/nsxt_ether_type_ns_service.md)

- [nsxt_firewall_section](./r/nsxt_firewall_section.md)

- [nsxt_icmp_type_ns_service](./r/nsxt_icmp_type_ns_service.md)

- [nsxt_igmp_type_ns_service](./r/nsxt_igmp_type_ns_service.md)

- [nsxt_ip_block](./r/nsxt_ip_block.md)

- [nsxt_ip_block_subnet](./r/nsxt_ip_block_subnet.md)

- [nsxt_ip_discovery_switching_profile](./r/nsxt_ip_discovery_switching_profile.md)

- [nsxt_ip_pool](./r/nsxt_ip_pool.md)

- [nsxt_ip_pool_allocation_ip_address](./r/nsxt_ip_pool_allocation_ip_address.md)

- [nsxt_ip_protocol_ns_service](./r/nsxt_ip_protocol_ns_service.md)

- [nsxt_ip_set](./r/nsxt_ip_set.md)

- [nsxt_l4_port_set_ns_service](./r/nsxt_l4_port_set_ns_service.md)

- [nsxt_lb_client_ssl_profile](./r/nsxt_lb_client_ssl_profile.md)

- [nsxt_lb_cookie_persistence_profile](./r/nsxt_lb_cookie_persistence_profile.md)

- [nsxt_lb_fast_tcp_application_profile](./r/nsxt_lb_fast_tcp_application_profile.md)

- [nsxt_lb_fast_udp_application_profile](./r/nsxt_lb_fast_udp_application_profile.md)

- [nsxt_lb_http_application_profile](./r/nsxt_lb_http_application_profile.md)

- [nsxt_lb_http_forwarding_rule](./r/nsxt_lb_http_forwarding_rule.md)

- [nsxt_lb_http_monitor](./r/nsxt_lb_http_monitor.md)

- [nsxt_lb_http_request_rewrite_rule](./r/nsxt_lb_http_request_rewrite_rule.md)

- [nsxt_lb_http_response_rewrite_rule](./r/nsxt_lb_http_response_rewrite_rule.md)

- [nsxt_lb_http_virtual_server](./r/nsxt_lb_http_virtual_server.md)

- [nsxt_lb_https_monitor](./r/nsxt_lb_https_monitor.md)

- [nsxt_lb_icmp_monitor](./r/nsxt_lb_icmp_monitor.md)

- [nsxt_lb_passive_monitor](./r/nsxt_lb_passive_monitor.md)

- [nsxt_lb_pool](./r/nsxt_lb_pool.md)

- [nsxt_lb_server_ssl_profile](./r/nsxt_lb_server_ssl_profile.md)

- [nsxt_lb_service](./r/nsxt_lb_service.md)

- [nsxt_lb_source_ip_persistence_profile](./r/nsxt_lb_source_ip_persistence_profile.md)

- [nsxt_lb_tcp_monitor](./r/nsxt_lb_tcp_monitor.md)

- [nsxt_lb_tcp_virtual_server](./r/nsxt_lb_tcp_virtual_server.md)

- [nsxt_lb_udp_monitor](./r/nsxt_lb_udp_monitor.md)

- [nsxt_lb_udp_virtual_server](./r/nsxt_lb_udp_virtual_server.md)

- [nsxt_logical_dhcp_port](./r/nsxt_logical_dhcp_port.md)

- [nsxt_logical_dhcp_server](./r/nsxt_logical_dhcp_server.md)

- [nsxt_logical_port](./r/nsxt_logical_port.md)

- [nsxt_logical_router_centralized_service_port](./r/nsxt_logical_router_centralized_service_port.md)

- [nsxt_logical_router_downlink_port](./r/nsxt_logical_router_downlink_port.md)

- [nsxt_logical_router_link_port_on_tier0](./r/nsxt_logical_router_link_port_on_tier0.md)

- [nsxt_logical_router_link_port_on_tier1](./r/nsxt_logical_router_link_port_on_tier1.md)

- [nsxt_logical_switch](./r/nsxt_logical_switch.md)

- [nsxt_logical_tier0_router](./r/nsxt_logical_tier0_router.md)

- [nsxt_logical_tier1_router](./r/nsxt_logical_tier1_router.md)

- [nsxt_mac_management_switching_profile](./r/nsxt_mac_management_switching_profile.md)

- [nsxt_nat_rule](./r/nsxt_nat_rule.md)

- [nsxt_ns_group](./r/nsxt_ns_group.md)

- [nsxt_ns_service_group](./r/nsxt_ns_service_group.md)

- [nsxt_policy_bgp_config](./r/nsxt_policy_bgp_config.md)

- [nsxt_policy_bgp_neighbor](./r/nsxt_policy_bgp_neighbor.md)

- [nsxt_policy_context_profile](./r/nsxt_policy_context_profile.md)

- [nsxt_policy_dhcp_relay](./r/nsxt_policy_dhcp_relay.md)

- [nsxt_policy_dhcp_server](./r/nsxt_policy_dhcp_server.md)

- [nsxt_policy_dhcp_v4_static_binding](./r/nsxt_policy_dhcp_v4_static_binding.md)

- [nsxt_policy_dhcp_v6_static_binding](./r/nsxt_policy_dhcp_v6_static_binding.md)

- [nsxt_policy_dns_forwarder_zone](./r/nsxt_policy_dns_forwarder_zone.md)

- [nsxt_policy_domain](./r/nsxt_policy_domain.md)

- [nsxt_policy_fixed_segment](./r/nsxt_policy_fixed_segment.md)

- [nsxt_policy_gateway_community_list](./r/nsxt_policy_gateway_community_list.md)

- [nsxt_policy_gateway_dns_forwarder](./r/nsxt_policy_gateway_dns_forwarder.md)

- [nsxt_policy_gateway_policy](./r/nsxt_policy_gateway_policy.md)

- [nsxt_policy_gateway_prefix_list](./r/nsxt_policy_gateway_prefix_list.md)

- [nsxt_policy_group](./r/nsxt_policy_group.md)

- [nsxt_policy_intrusion_service_policy](./r/nsxt_policy_intrusion_service_policy.md)

- [nsxt_policy_ip_address_allocation](./r/nsxt_policy_ip_address_allocation.md)

- [nsxt_policy_ip_block](./r/nsxt_policy_ip_block.md)

- [nsxt_policy_ip_pool](./r/nsxt_policy_ip_pool.md)

- [nsxt_policy_ip_pool_block_subnet](./r/nsxt_policy_ip_pool_block_subnet.md)

- [nsxt_policy_ip_pool_static_subnet](./r/nsxt_policy_ip_pool_static_subnet.md)

- [nsxt_policy_lb_pool](./r/nsxt_policy_lb_pool.md)

- [nsxt_policy_lb_service](./r/nsxt_policy_lb_service.md)

- [nsxt_policy_lb_virtual_server](./r/nsxt_policy_lb_virtual_server.md)

- [nsxt_policy_nat_rule](./r/nsxt_policy_nat_rule.md)

- [nsxt_policy_predefined_gateway_policy](./r/nsxt_policy_predefined_gateway_policy.md)

- [nsxt_policy_predefined_security_policy](./r/nsxt_policy_predefined_security_policy.md)

- [nsxt_policy_security_policy](./r/nsxt_policy_security_policy.md)

- [nsxt_policy_segment](./r/nsxt_policy_segment.md)

- [nsxt_policy_service](./r/nsxt_policy_service.md)

- [nsxt_policy_static_route](./r/nsxt_policy_static_route.md)

- [nsxt_policy_tier0_gateway](./r/nsxt_policy_tier0_gateway.md)

- [nsxt_policy_tier0_gateway_ha_vip_config](./r/nsxt_policy_tier0_gateway_ha_vip_config.md)

- [nsxt_policy_tier0_gateway_interface](./r/nsxt_policy_tier0_gateway_interface.md)

- [nsxt_policy_tier1_gateway](./r/nsxt_policy_tier1_gateway.md)

- [nsxt_policy_tier1_gateway_interface](./r/nsxt_policy_tier1_gateway_interface.md)

- [nsxt_policy_vlan_segment](./r/nsxt_policy_vlan_segment.md)

- [nsxt_policy_vm_tags](./r/nsxt_policy_vm_tags.md)

- [nsxt_qos_switching_profile](./r/nsxt_qos_switching_profile.md)

- [nsxt_spoofguard_switching_profile](./r/nsxt_spoofguard_switching_profile.md)

- [nsxt_static_route](./r/nsxt_static_route.md)

- [nsxt_switch_security_switching_profile](./r/nsxt_switch_security_switching_profile.md)

- [nsxt_vlan_logical_switch](./r/nsxt_vlan_logical_switch.md)

- [nsxt_vm_tags](./r/nsxt_vm_tags.md)


[top](#index)

### Datasources


- [nsxt_certificate](./d/nsxt_certificate.md)

- [nsxt_edge_cluster](./d/nsxt_edge_cluster.md)

- [nsxt_firewall_section](./d/nsxt_firewall_section.md)

- [nsxt_ip_pool](./d/nsxt_ip_pool.md)

- [nsxt_logical_tier0_router](./d/nsxt_logical_tier0_router.md)

- [nsxt_logical_tier1_router](./d/nsxt_logical_tier1_router.md)

- [nsxt_mac_pool](./d/nsxt_mac_pool.md)

- [nsxt_management_cluster](./d/nsxt_management_cluster.md)

- [nsxt_ns_group](./d/nsxt_ns_group.md)

- [nsxt_ns_service](./d/nsxt_ns_service.md)

- [nsxt_policy_bfd_profile](./d/nsxt_policy_bfd_profile.md)

- [nsxt_policy_certificate](./d/nsxt_policy_certificate.md)

- [nsxt_policy_context_profile](./d/nsxt_policy_context_profile.md)

- [nsxt_policy_dhcp_server](./d/nsxt_policy_dhcp_server.md)

- [nsxt_policy_edge_cluster](./d/nsxt_policy_edge_cluster.md)

- [nsxt_policy_edge_node](./d/nsxt_policy_edge_node.md)

- [nsxt_policy_gateway_policy](./d/nsxt_policy_gateway_policy.md)

- [nsxt_policy_gateway_qos_profile](./d/nsxt_policy_gateway_qos_profile.md)

- [nsxt_policy_group](./d/nsxt_policy_group.md)

- [nsxt_policy_ip_block](./d/nsxt_policy_ip_block.md)

- [nsxt_policy_ip_discovery_profile](./d/nsxt_policy_ip_discovery_profile.md)

- [nsxt_policy_ip_pool](./d/nsxt_policy_ip_pool.md)

- [nsxt_policy_ipv6_dad_profile](./d/nsxt_policy_ipv6_dad_profile.md)

- [nsxt_policy_ipv6_ndra_profile](./d/nsxt_policy_ipv6_ndra_profile.md)

- [nsxt_policy_lb_app_profile](./d/nsxt_policy_lb_app_profile.md)

- [nsxt_policy_lb_client_ssl_profile](./d/nsxt_policy_lb_client_ssl_profile.md)

- [nsxt_policy_lb_monitor](./d/nsxt_policy_lb_monitor.md)

- [nsxt_policy_lb_persistence_profile](./d/nsxt_policy_lb_persistence_profile.md)

- [nsxt_policy_lb_server_ssl_profile](./d/nsxt_policy_lb_server_ssl_profile.md)

- [nsxt_policy_mac_discovery_profile](./d/nsxt_policy_mac_discovery_profile.md)

- [nsxt_policy_qos_profile](./d/nsxt_policy_qos_profile.md)

- [nsxt_policy_realization_info](./d/nsxt_policy_realization_info.md)

- [nsxt_policy_security_policy](./d/nsxt_policy_security_policy.md)

- [nsxt_policy_segment_realization](./d/nsxt_policy_segment_realization.md)

- [nsxt_policy_segment_security_profile](./d/nsxt_policy_segment_security_profile.md)

- [nsxt_policy_service](./d/nsxt_policy_service.md)

- [nsxt_policy_site](./d/nsxt_policy_site.md)

- [nsxt_policy_spoofguard_profile](./d/nsxt_policy_spoofguard_profile.md)

- [nsxt_policy_tier0_gateway](./d/nsxt_policy_tier0_gateway.md)

- [nsxt_policy_tier1_gateway](./d/nsxt_policy_tier1_gateway.md)

- [nsxt_policy_transport_zone](./d/nsxt_policy_transport_zone.md)

- [nsxt_policy_vm](./d/nsxt_policy_vm.md)

- [nsxt_policy_vni_pool](./d/nsxt_policy_vni_pool.md)

- [nsxt_provider_info](./d/nsxt_provider_info.md)

- [nsxt_switching_profile](./d/nsxt_switching_profile.md)

- [nsxt_transport_zone](./d/nsxt_transport_zone.md)


[top](#index)