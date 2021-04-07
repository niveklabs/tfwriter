# fortios_system_interface

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_interface" {
  source = "./modules/fortios/d/fortios_system_interface"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_interface" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "ac_name" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ac_name
}

output "aggregate" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.aggregate
}

output "algorithm" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.algorithm
}

output "alias" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.alias
}

output "allowaccess" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.allowaccess
}

output "ap_discover" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ap_discover
}

output "arpforward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.arpforward
}

output "auth_type" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.auth_type
}

output "auto_auth_extension_device" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.auto_auth_extension_device
}

output "bandwidth_measure_time" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.bandwidth_measure_time
}

output "bfd" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.bfd
}

output "bfd_desired_min_tx" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.bfd_desired_min_tx
}

output "bfd_detect_mult" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.bfd_detect_mult
}

output "bfd_required_min_rx" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.bfd_required_min_rx
}

output "broadcast_forticlient_discovery" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.broadcast_forticlient_discovery
}

output "broadcast_forward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.broadcast_forward
}

output "captive_portal" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.captive_portal
}

output "cli_conn_status" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.cli_conn_status
}

output "client_options" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.client_options
}

output "color" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.color
}

output "dedicated_to" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dedicated_to
}

output "defaultgw" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.defaultgw
}

output "description" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.description
}

output "detected_peer_mtu" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.detected_peer_mtu
}

output "detectprotocol" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.detectprotocol
}

output "detectserver" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.detectserver
}

output "device_access_list" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.device_access_list
}

output "device_identification" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.device_identification
}

output "device_identification_active_scan" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.device_identification_active_scan
}

output "device_netscan" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.device_netscan
}

output "device_user_identification" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.device_user_identification
}

output "devindex" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.devindex
}

output "dhcp_client_identifier" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_client_identifier
}

output "dhcp_relay_agent_option" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_relay_agent_option
}

output "dhcp_relay_interface" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_relay_interface
}

output "dhcp_relay_interface_select_method" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_relay_interface_select_method
}

output "dhcp_relay_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_relay_ip
}

output "dhcp_relay_service" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_relay_service
}

output "dhcp_relay_type" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dhcp_relay_type
}

output "dhcp_renew_time" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.dhcp_renew_time
}

output "disc_retry_timeout" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.disc_retry_timeout
}

output "disconnect_threshold" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.disconnect_threshold
}

output "distance" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.distance
}

output "dns_server_override" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.dns_server_override
}

output "drop_fragment" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.drop_fragment
}

output "drop_overlapped_fragment" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.drop_overlapped_fragment
}

output "egress_shaping_profile" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.egress_shaping_profile
}

output "endpoint_compliance" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.endpoint_compliance
}

output "estimated_downstream_bandwidth" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.estimated_downstream_bandwidth
}

output "estimated_upstream_bandwidth" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.estimated_upstream_bandwidth
}

output "explicit_ftp_proxy" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.explicit_ftp_proxy
}

output "explicit_web_proxy" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.explicit_web_proxy
}

output "external" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.external
}

output "fail_action_on_extender" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fail_action_on_extender
}

output "fail_alert_interfaces" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.fail_alert_interfaces
}

output "fail_alert_method" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fail_alert_method
}

output "fail_detect" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fail_detect
}

output "fail_detect_option" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fail_detect_option
}

output "fortiheartbeat" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fortiheartbeat
}

output "fortilink" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fortilink
}

output "fortilink_backup_link" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.fortilink_backup_link
}

output "fortilink_neighbor_detect" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fortilink_neighbor_detect
}

output "fortilink_split_interface" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fortilink_split_interface
}

output "fortilink_stacking" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.fortilink_stacking
}

output "forward_domain" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.forward_domain
}

output "gwdetect" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.gwdetect
}

output "ha_priority" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.ha_priority
}

output "icmp_accept_redirect" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.icmp_accept_redirect
}

output "icmp_send_redirect" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.icmp_send_redirect
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.id
}

output "ident_accept" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ident_accept
}

output "idle_timeout" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.idle_timeout
}

output "inbandwidth" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.inbandwidth
}

output "ingress_shaping_profile" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ingress_shaping_profile
}

output "ingress_spillover_threshold" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.ingress_spillover_threshold
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.interface
}

output "internal" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.internal
}

output "ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ip
}

output "ip_managed_by_fortiipam" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ip_managed_by_fortiipam
}

output "ipmac" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ipmac
}

output "ips_sniffer_mode" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ips_sniffer_mode
}

output "ipunnumbered" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ipunnumbered
}

output "ipv6" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.ipv6
}

output "l2forward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.l2forward
}

output "lacp_ha_slave" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.lacp_ha_slave
}

output "lacp_mode" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.lacp_mode
}

output "lacp_speed" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.lacp_speed
}

output "lcp_echo_interval" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.lcp_echo_interval
}

output "lcp_max_echo_fails" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.lcp_max_echo_fails
}

output "link_up_delay" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.link_up_delay
}

output "lldp_network_policy" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.lldp_network_policy
}

output "lldp_reception" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.lldp_reception
}

output "lldp_transmission" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.lldp_transmission
}

output "macaddr" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.macaddr
}

output "managed_device" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.managed_device
}

output "managed_subnetwork_size" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.managed_subnetwork_size
}

output "management_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.management_ip
}

output "measured_downstream_bandwidth" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.measured_downstream_bandwidth
}

output "measured_upstream_bandwidth" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.measured_upstream_bandwidth
}

output "member" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.member
}

output "min_links" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.min_links
}

output "min_links_down" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.min_links_down
}

output "mode" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.mode
}

output "monitor_bandwidth" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.monitor_bandwidth
}

output "mtu" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.mtu
}

output "mtu_override" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.mtu_override
}

output "ndiscforward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.ndiscforward
}

output "netbios_forward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.netbios_forward
}

output "netflow_sampler" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.netflow_sampler
}

output "outbandwidth" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.outbandwidth
}

output "padt_retry_timeout" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.padt_retry_timeout
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.password
  sensitive   = true
}

output "ping_serv_status" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.ping_serv_status
}

output "polling_interval" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.polling_interval
}

output "pppoe_unnumbered_negotiate" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.pppoe_unnumbered_negotiate
}

output "pptp_auth_type" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.pptp_auth_type
}

output "pptp_client" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.pptp_client
}

output "pptp_password" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.pptp_password
  sensitive   = true
}

output "pptp_server_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.pptp_server_ip
}

output "pptp_timeout" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.pptp_timeout
}

output "pptp_user" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.pptp_user
}

output "preserve_session_route" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.preserve_session_route
}

output "priority" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.priority
}

output "priority_override" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.priority_override
}

output "proxy_captive_portal" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.proxy_captive_portal
}

output "redundant_interface" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.redundant_interface
}

output "remote_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.remote_ip
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.replacemsg_override_group
}

output "ring_rx" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.ring_rx
}

output "ring_tx" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.ring_tx
}

output "role" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.role
}

output "sample_direction" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.sample_direction
}

output "sample_rate" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.sample_rate
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.scan_botnet_connections
}

output "secondary_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.secondary_ip
}

output "secondaryip" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.secondaryip
}

output "security_exempt_list" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.security_exempt_list
}

output "security_external_logout" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.security_external_logout
}

output "security_external_web" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.security_external_web
}

output "security_groups" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.security_groups
}

output "security_mac_auth_bypass" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.security_mac_auth_bypass
}

output "security_mode" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.security_mode
}

output "security_redirect_url" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.security_redirect_url
}

output "service_name" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.service_name
}

output "sflow_sampler" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.sflow_sampler
}

output "snmp_index" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.snmp_index
}

output "speed" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.speed
}

output "spillover_threshold" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.spillover_threshold
}

output "src_check" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.src_check
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.status
}

output "stpforward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.stpforward
}

output "stpforward_mode" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.stpforward_mode
}

output "subst" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.subst
}

output "substitute_dst_mac" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.substitute_dst_mac
}

output "swc_first_create" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.swc_first_create
}

output "swc_vlan" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.swc_vlan
}

output "switch" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch
}

output "switch_controller_access_vlan" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_access_vlan
}

output "switch_controller_arp_inspection" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_arp_inspection
}

output "switch_controller_dhcp_snooping" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_dhcp_snooping
}

output "switch_controller_dhcp_snooping_option82" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_dhcp_snooping_option82
}

output "switch_controller_dhcp_snooping_verify_mac" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_dhcp_snooping_verify_mac
}

output "switch_controller_feature" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_feature
}

output "switch_controller_igmp_snooping" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_igmp_snooping
}

output "switch_controller_igmp_snooping_fast_leave" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_igmp_snooping_fast_leave
}

output "switch_controller_igmp_snooping_proxy" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_igmp_snooping_proxy
}

output "switch_controller_iot_scanning" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_iot_scanning
}

output "switch_controller_learning_limit" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.switch_controller_learning_limit
}

output "switch_controller_mgmt_vlan" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.switch_controller_mgmt_vlan
}

output "switch_controller_nac" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_nac
}

output "switch_controller_rspan_mode" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_rspan_mode
}

output "switch_controller_source_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_source_ip
}

output "switch_controller_traffic_policy" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.switch_controller_traffic_policy
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.tagging
}

output "tcp_mss" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.tcp_mss
}

output "trust_ip6_1" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.trust_ip6_1
}

output "trust_ip6_2" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.trust_ip6_2
}

output "trust_ip6_3" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.trust_ip6_3
}

output "trust_ip_1" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.trust_ip_1
}

output "trust_ip_2" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.trust_ip_2
}

output "trust_ip_3" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.trust_ip_3
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.type
}

output "username" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.username
}

output "vdom" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.vdom
}

output "vindex" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.vindex
}

output "vlan_protocol" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.vlan_protocol
}

output "vlanforward" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.vlanforward
}

output "vlanid" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.vlanid
}

output "vrf" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.vrf
}

output "vrrp" {
  description = "returns a list of object"
  value       = data.fortios_system_interface.this.vrrp
}

output "vrrp_virtual_mac" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.vrrp_virtual_mac
}

output "wccp" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.wccp
}

output "weight" {
  description = "returns a number"
  value       = data.fortios_system_interface.this.weight
}

output "wins_ip" {
  description = "returns a string"
  value       = data.fortios_system_interface.this.wins_ip
}

output "this" {
  value = fortios_system_interface.this
}
```

[top](#index)