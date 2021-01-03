# fortios_system_settings

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_settings" {
  source = "./modules/fortios/r/fortios_system_settings"

  # allow_linkdown_path - (optional) is a type of string
  allow_linkdown_path = null
  # allow_subnet_overlap - (optional) is a type of string
  allow_subnet_overlap = null
  # asymroute - (optional) is a type of string
  asymroute = null
  # asymroute6 - (optional) is a type of string
  asymroute6 = null
  # asymroute6_icmp - (optional) is a type of string
  asymroute6_icmp = null
  # asymroute_icmp - (optional) is a type of string
  asymroute_icmp = null
  # bfd - (optional) is a type of string
  bfd = null
  # bfd_desired_min_tx - (optional) is a type of number
  bfd_desired_min_tx = null
  # bfd_detect_mult - (optional) is a type of number
  bfd_detect_mult = null
  # bfd_dont_enforce_src_port - (optional) is a type of string
  bfd_dont_enforce_src_port = null
  # bfd_required_min_rx - (optional) is a type of number
  bfd_required_min_rx = null
  # block_land_attack - (optional) is a type of string
  block_land_attack = null
  # central_nat - (optional) is a type of string
  central_nat = null
  # comments - (optional) is a type of string
  comments = null
  # compliance_check - (optional) is a type of string
  compliance_check = null
  # consolidated_firewall_mode - (optional) is a type of string
  consolidated_firewall_mode = null
  # default_voip_alg_mode - (optional) is a type of string
  default_voip_alg_mode = null
  # deny_tcp_with_icmp - (optional) is a type of string
  deny_tcp_with_icmp = null
  # device - (optional) is a type of string
  device = null
  # dhcp6_server_ip - (optional) is a type of string
  dhcp6_server_ip = null
  # dhcp_proxy - (optional) is a type of string
  dhcp_proxy = null
  # dhcp_server_ip - (optional) is a type of string
  dhcp_server_ip = null
  # discovered_device_timeout - (optional) is a type of number
  discovered_device_timeout = null
  # ecmp_max_paths - (optional) is a type of number
  ecmp_max_paths = null
  # email_portal_check_dns - (optional) is a type of string
  email_portal_check_dns = null
  # firewall_session_dirty - (optional) is a type of string
  firewall_session_dirty = null
  # fw_session_hairpin - (optional) is a type of string
  fw_session_hairpin = null
  # gateway - (optional) is a type of string
  gateway = null
  # gateway6 - (optional) is a type of string
  gateway6 = null
  # gui_advanced_policy - (optional) is a type of string
  gui_advanced_policy = null
  # gui_allow_unnamed_policy - (optional) is a type of string
  gui_allow_unnamed_policy = null
  # gui_antivirus - (optional) is a type of string
  gui_antivirus = null
  # gui_ap_profile - (optional) is a type of string
  gui_ap_profile = null
  # gui_application_control - (optional) is a type of string
  gui_application_control = null
  # gui_dhcp_advanced - (optional) is a type of string
  gui_dhcp_advanced = null
  # gui_dlp - (optional) is a type of string
  gui_dlp = null
  # gui_dns_database - (optional) is a type of string
  gui_dns_database = null
  # gui_dnsfilter - (optional) is a type of string
  gui_dnsfilter = null
  # gui_domain_ip_reputation - (optional) is a type of string
  gui_domain_ip_reputation = null
  # gui_dos_policy - (optional) is a type of string
  gui_dos_policy = null
  # gui_dynamic_profile_display - (optional) is a type of string
  gui_dynamic_profile_display = null
  # gui_dynamic_routing - (optional) is a type of string
  gui_dynamic_routing = null
  # gui_email_collection - (optional) is a type of string
  gui_email_collection = null
  # gui_endpoint_control - (optional) is a type of string
  gui_endpoint_control = null
  # gui_endpoint_control_advanced - (optional) is a type of string
  gui_endpoint_control_advanced = null
  # gui_explicit_proxy - (optional) is a type of string
  gui_explicit_proxy = null
  # gui_fortiap_split_tunneling - (optional) is a type of string
  gui_fortiap_split_tunneling = null
  # gui_fortiextender_controller - (optional) is a type of string
  gui_fortiextender_controller = null
  # gui_icap - (optional) is a type of string
  gui_icap = null
  # gui_implicit_policy - (optional) is a type of string
  gui_implicit_policy = null
  # gui_ips - (optional) is a type of string
  gui_ips = null
  # gui_load_balance - (optional) is a type of string
  gui_load_balance = null
  # gui_local_in_policy - (optional) is a type of string
  gui_local_in_policy = null
  # gui_local_reports - (optional) is a type of string
  gui_local_reports = null
  # gui_multicast_policy - (optional) is a type of string
  gui_multicast_policy = null
  # gui_multiple_interface_policy - (optional) is a type of string
  gui_multiple_interface_policy = null
  # gui_multiple_utm_profiles - (optional) is a type of string
  gui_multiple_utm_profiles = null
  # gui_nat46_64 - (optional) is a type of string
  gui_nat46_64 = null
  # gui_object_colors - (optional) is a type of string
  gui_object_colors = null
  # gui_policy_based_ipsec - (optional) is a type of string
  gui_policy_based_ipsec = null
  # gui_policy_learning - (optional) is a type of string
  gui_policy_learning = null
  # gui_replacement_message_groups - (optional) is a type of string
  gui_replacement_message_groups = null
  # gui_spamfilter - (optional) is a type of string
  gui_spamfilter = null
  # gui_sslvpn_personal_bookmarks - (optional) is a type of string
  gui_sslvpn_personal_bookmarks = null
  # gui_sslvpn_realms - (optional) is a type of string
  gui_sslvpn_realms = null
  # gui_switch_controller - (optional) is a type of string
  gui_switch_controller = null
  # gui_threat_weight - (optional) is a type of string
  gui_threat_weight = null
  # gui_traffic_shaping - (optional) is a type of string
  gui_traffic_shaping = null
  # gui_voip_profile - (optional) is a type of string
  gui_voip_profile = null
  # gui_vpn - (optional) is a type of string
  gui_vpn = null
  # gui_waf_profile - (optional) is a type of string
  gui_waf_profile = null
  # gui_wan_load_balancing - (optional) is a type of string
  gui_wan_load_balancing = null
  # gui_wanopt_cache - (optional) is a type of string
  gui_wanopt_cache = null
  # gui_webfilter - (optional) is a type of string
  gui_webfilter = null
  # gui_webfilter_advanced - (optional) is a type of string
  gui_webfilter_advanced = null
  # gui_wireless_controller - (optional) is a type of string
  gui_wireless_controller = null
  # http_external_dest - (optional) is a type of string
  http_external_dest = null
  # ike_dn_format - (optional) is a type of string
  ike_dn_format = null
  # ike_quick_crash_detect - (optional) is a type of string
  ike_quick_crash_detect = null
  # ike_session_resume - (optional) is a type of string
  ike_session_resume = null
  # implicit_allow_dns - (optional) is a type of string
  implicit_allow_dns = null
  # inspection_mode - (optional) is a type of string
  inspection_mode = null
  # ip - (optional) is a type of string
  ip = null
  # ip6 - (optional) is a type of string
  ip6 = null
  # link_down_access - (optional) is a type of string
  link_down_access = null
  # lldp_reception - (optional) is a type of string
  lldp_reception = null
  # lldp_transmission - (optional) is a type of string
  lldp_transmission = null
  # mac_ttl - (optional) is a type of number
  mac_ttl = null
  # manageip - (optional) is a type of string
  manageip = null
  # manageip6 - (optional) is a type of string
  manageip6 = null
  # multicast_forward - (optional) is a type of string
  multicast_forward = null
  # multicast_skip_policy - (optional) is a type of string
  multicast_skip_policy = null
  # multicast_ttl_notchange - (optional) is a type of string
  multicast_ttl_notchange = null
  # ngfw_mode - (optional) is a type of string
  ngfw_mode = null
  # opmode - (optional) is a type of string
  opmode = null
  # prp_trailer_action - (optional) is a type of string
  prp_trailer_action = null
  # sccp_port - (optional) is a type of number
  sccp_port = null
  # ses_denied_traffic - (optional) is a type of string
  ses_denied_traffic = null
  # sip_helper - (optional) is a type of string
  sip_helper = null
  # sip_nat_trace - (optional) is a type of string
  sip_nat_trace = null
  # sip_ssl_port - (optional) is a type of number
  sip_ssl_port = null
  # sip_tcp_port - (optional) is a type of number
  sip_tcp_port = null
  # sip_udp_port - (optional) is a type of number
  sip_udp_port = null
  # snat_hairpin_traffic - (optional) is a type of string
  snat_hairpin_traffic = null
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = null
  # status - (optional) is a type of string
  status = null
  # strict_src_check - (optional) is a type of string
  strict_src_check = null
  # tcp_session_without_syn - (optional) is a type of string
  tcp_session_without_syn = null
  # utf8_spam_tagging - (optional) is a type of string
  utf8_spam_tagging = null
  # v4_ecmp_mode - (optional) is a type of string
  v4_ecmp_mode = null
  # vpn_stats_log - (optional) is a type of string
  vpn_stats_log = null
  # vpn_stats_period - (optional) is a type of number
  vpn_stats_period = null
  # wccp_cache_engine - (optional) is a type of string
  wccp_cache_engine = null

  gui_default_policy_columns = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_linkdown_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_subnet_overlap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "asymroute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "asymroute6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "asymroute6_icmp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "asymroute_icmp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bfd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bfd_desired_min_tx" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bfd_detect_mult" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bfd_dont_enforce_src_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bfd_required_min_rx" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "block_land_attack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "central_nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compliance_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "consolidated_firewall_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_voip_alg_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deny_tcp_with_icmp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp6_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "discovered_device_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ecmp_max_paths" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "email_portal_check_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_session_dirty" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fw_session_hairpin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_advanced_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_allow_unnamed_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_antivirus" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_ap_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_application_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dhcp_advanced" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dlp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dns_database" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dnsfilter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_domain_ip_reputation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dos_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dynamic_profile_display" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_dynamic_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_email_collection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_endpoint_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_endpoint_control_advanced" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_explicit_proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_fortiap_split_tunneling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_fortiextender_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_icap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_implicit_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_ips" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_load_balance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_local_in_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_local_reports" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_multicast_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_multiple_interface_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_multiple_utm_profiles" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_nat46_64" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_object_colors" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_policy_based_ipsec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_policy_learning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_replacement_message_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_spamfilter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_sslvpn_personal_bookmarks" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_sslvpn_realms" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_switch_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_threat_weight" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_traffic_shaping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_voip_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_vpn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_waf_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_wan_load_balancing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_wanopt_cache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_webfilter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_webfilter_advanced" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_wireless_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_external_dest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ike_dn_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ike_quick_crash_detect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ike_session_resume" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "implicit_allow_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_down_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp_reception" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp_transmission" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "manageip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "manageip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_skip_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_ttl_notchange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ngfw_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opmode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prp_trailer_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sccp_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ses_denied_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sip_helper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sip_nat_trace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sip_ssl_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sip_tcp_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sip_udp_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat_hairpin_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_ssh_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_src_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_session_without_syn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "utf8_spam_tagging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "v4_ecmp_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_stats_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_stats_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wccp_cache_engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_default_policy_columns" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_settings" "this" {
  allow_linkdown_path            = var.allow_linkdown_path
  allow_subnet_overlap           = var.allow_subnet_overlap
  asymroute                      = var.asymroute
  asymroute6                     = var.asymroute6
  asymroute6_icmp                = var.asymroute6_icmp
  asymroute_icmp                 = var.asymroute_icmp
  bfd                            = var.bfd
  bfd_desired_min_tx             = var.bfd_desired_min_tx
  bfd_detect_mult                = var.bfd_detect_mult
  bfd_dont_enforce_src_port      = var.bfd_dont_enforce_src_port
  bfd_required_min_rx            = var.bfd_required_min_rx
  block_land_attack              = var.block_land_attack
  central_nat                    = var.central_nat
  comments                       = var.comments
  compliance_check               = var.compliance_check
  consolidated_firewall_mode     = var.consolidated_firewall_mode
  default_voip_alg_mode          = var.default_voip_alg_mode
  deny_tcp_with_icmp             = var.deny_tcp_with_icmp
  device                         = var.device
  dhcp6_server_ip                = var.dhcp6_server_ip
  dhcp_proxy                     = var.dhcp_proxy
  dhcp_server_ip                 = var.dhcp_server_ip
  discovered_device_timeout      = var.discovered_device_timeout
  ecmp_max_paths                 = var.ecmp_max_paths
  email_portal_check_dns         = var.email_portal_check_dns
  firewall_session_dirty         = var.firewall_session_dirty
  fw_session_hairpin             = var.fw_session_hairpin
  gateway                        = var.gateway
  gateway6                       = var.gateway6
  gui_advanced_policy            = var.gui_advanced_policy
  gui_allow_unnamed_policy       = var.gui_allow_unnamed_policy
  gui_antivirus                  = var.gui_antivirus
  gui_ap_profile                 = var.gui_ap_profile
  gui_application_control        = var.gui_application_control
  gui_dhcp_advanced              = var.gui_dhcp_advanced
  gui_dlp                        = var.gui_dlp
  gui_dns_database               = var.gui_dns_database
  gui_dnsfilter                  = var.gui_dnsfilter
  gui_domain_ip_reputation       = var.gui_domain_ip_reputation
  gui_dos_policy                 = var.gui_dos_policy
  gui_dynamic_profile_display    = var.gui_dynamic_profile_display
  gui_dynamic_routing            = var.gui_dynamic_routing
  gui_email_collection           = var.gui_email_collection
  gui_endpoint_control           = var.gui_endpoint_control
  gui_endpoint_control_advanced  = var.gui_endpoint_control_advanced
  gui_explicit_proxy             = var.gui_explicit_proxy
  gui_fortiap_split_tunneling    = var.gui_fortiap_split_tunneling
  gui_fortiextender_controller   = var.gui_fortiextender_controller
  gui_icap                       = var.gui_icap
  gui_implicit_policy            = var.gui_implicit_policy
  gui_ips                        = var.gui_ips
  gui_load_balance               = var.gui_load_balance
  gui_local_in_policy            = var.gui_local_in_policy
  gui_local_reports              = var.gui_local_reports
  gui_multicast_policy           = var.gui_multicast_policy
  gui_multiple_interface_policy  = var.gui_multiple_interface_policy
  gui_multiple_utm_profiles      = var.gui_multiple_utm_profiles
  gui_nat46_64                   = var.gui_nat46_64
  gui_object_colors              = var.gui_object_colors
  gui_policy_based_ipsec         = var.gui_policy_based_ipsec
  gui_policy_learning            = var.gui_policy_learning
  gui_replacement_message_groups = var.gui_replacement_message_groups
  gui_spamfilter                 = var.gui_spamfilter
  gui_sslvpn_personal_bookmarks  = var.gui_sslvpn_personal_bookmarks
  gui_sslvpn_realms              = var.gui_sslvpn_realms
  gui_switch_controller          = var.gui_switch_controller
  gui_threat_weight              = var.gui_threat_weight
  gui_traffic_shaping            = var.gui_traffic_shaping
  gui_voip_profile               = var.gui_voip_profile
  gui_vpn                        = var.gui_vpn
  gui_waf_profile                = var.gui_waf_profile
  gui_wan_load_balancing         = var.gui_wan_load_balancing
  gui_wanopt_cache               = var.gui_wanopt_cache
  gui_webfilter                  = var.gui_webfilter
  gui_webfilter_advanced         = var.gui_webfilter_advanced
  gui_wireless_controller        = var.gui_wireless_controller
  http_external_dest             = var.http_external_dest
  ike_dn_format                  = var.ike_dn_format
  ike_quick_crash_detect         = var.ike_quick_crash_detect
  ike_session_resume             = var.ike_session_resume
  implicit_allow_dns             = var.implicit_allow_dns
  inspection_mode                = var.inspection_mode
  ip                             = var.ip
  ip6                            = var.ip6
  link_down_access               = var.link_down_access
  lldp_reception                 = var.lldp_reception
  lldp_transmission              = var.lldp_transmission
  mac_ttl                        = var.mac_ttl
  manageip                       = var.manageip
  manageip6                      = var.manageip6
  multicast_forward              = var.multicast_forward
  multicast_skip_policy          = var.multicast_skip_policy
  multicast_ttl_notchange        = var.multicast_ttl_notchange
  ngfw_mode                      = var.ngfw_mode
  opmode                         = var.opmode
  prp_trailer_action             = var.prp_trailer_action
  sccp_port                      = var.sccp_port
  ses_denied_traffic             = var.ses_denied_traffic
  sip_helper                     = var.sip_helper
  sip_nat_trace                  = var.sip_nat_trace
  sip_ssl_port                   = var.sip_ssl_port
  sip_tcp_port                   = var.sip_tcp_port
  sip_udp_port                   = var.sip_udp_port
  snat_hairpin_traffic           = var.snat_hairpin_traffic
  ssl_ssh_profile                = var.ssl_ssh_profile
  status                         = var.status
  strict_src_check               = var.strict_src_check
  tcp_session_without_syn        = var.tcp_session_without_syn
  utf8_spam_tagging              = var.utf8_spam_tagging
  v4_ecmp_mode                   = var.v4_ecmp_mode
  vpn_stats_log                  = var.vpn_stats_log
  vpn_stats_period               = var.vpn_stats_period
  wccp_cache_engine              = var.wccp_cache_engine

  dynamic "gui_default_policy_columns" {
    for_each = var.gui_default_policy_columns
    content {
      name = gui_default_policy_columns.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_linkdown_path" {
  description = "returns a string"
  value       = fortios_system_settings.this.allow_linkdown_path
}

output "allow_subnet_overlap" {
  description = "returns a string"
  value       = fortios_system_settings.this.allow_subnet_overlap
}

output "asymroute" {
  description = "returns a string"
  value       = fortios_system_settings.this.asymroute
}

output "asymroute6" {
  description = "returns a string"
  value       = fortios_system_settings.this.asymroute6
}

output "asymroute6_icmp" {
  description = "returns a string"
  value       = fortios_system_settings.this.asymroute6_icmp
}

output "asymroute_icmp" {
  description = "returns a string"
  value       = fortios_system_settings.this.asymroute_icmp
}

output "bfd" {
  description = "returns a string"
  value       = fortios_system_settings.this.bfd
}

output "bfd_desired_min_tx" {
  description = "returns a number"
  value       = fortios_system_settings.this.bfd_desired_min_tx
}

output "bfd_detect_mult" {
  description = "returns a number"
  value       = fortios_system_settings.this.bfd_detect_mult
}

output "bfd_dont_enforce_src_port" {
  description = "returns a string"
  value       = fortios_system_settings.this.bfd_dont_enforce_src_port
}

output "bfd_required_min_rx" {
  description = "returns a number"
  value       = fortios_system_settings.this.bfd_required_min_rx
}

output "block_land_attack" {
  description = "returns a string"
  value       = fortios_system_settings.this.block_land_attack
}

output "central_nat" {
  description = "returns a string"
  value       = fortios_system_settings.this.central_nat
}

output "compliance_check" {
  description = "returns a string"
  value       = fortios_system_settings.this.compliance_check
}

output "consolidated_firewall_mode" {
  description = "returns a string"
  value       = fortios_system_settings.this.consolidated_firewall_mode
}

output "default_voip_alg_mode" {
  description = "returns a string"
  value       = fortios_system_settings.this.default_voip_alg_mode
}

output "deny_tcp_with_icmp" {
  description = "returns a string"
  value       = fortios_system_settings.this.deny_tcp_with_icmp
}

output "device" {
  description = "returns a string"
  value       = fortios_system_settings.this.device
}

output "dhcp6_server_ip" {
  description = "returns a string"
  value       = fortios_system_settings.this.dhcp6_server_ip
}

output "dhcp_proxy" {
  description = "returns a string"
  value       = fortios_system_settings.this.dhcp_proxy
}

output "dhcp_server_ip" {
  description = "returns a string"
  value       = fortios_system_settings.this.dhcp_server_ip
}

output "discovered_device_timeout" {
  description = "returns a number"
  value       = fortios_system_settings.this.discovered_device_timeout
}

output "ecmp_max_paths" {
  description = "returns a number"
  value       = fortios_system_settings.this.ecmp_max_paths
}

output "email_portal_check_dns" {
  description = "returns a string"
  value       = fortios_system_settings.this.email_portal_check_dns
}

output "firewall_session_dirty" {
  description = "returns a string"
  value       = fortios_system_settings.this.firewall_session_dirty
}

output "fw_session_hairpin" {
  description = "returns a string"
  value       = fortios_system_settings.this.fw_session_hairpin
}

output "gateway" {
  description = "returns a string"
  value       = fortios_system_settings.this.gateway
}

output "gateway6" {
  description = "returns a string"
  value       = fortios_system_settings.this.gateway6
}

output "gui_advanced_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_advanced_policy
}

output "gui_allow_unnamed_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_allow_unnamed_policy
}

output "gui_antivirus" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_antivirus
}

output "gui_ap_profile" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_ap_profile
}

output "gui_application_control" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_application_control
}

output "gui_dhcp_advanced" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dhcp_advanced
}

output "gui_dlp" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dlp
}

output "gui_dns_database" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dns_database
}

output "gui_dnsfilter" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dnsfilter
}

output "gui_domain_ip_reputation" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_domain_ip_reputation
}

output "gui_dos_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dos_policy
}

output "gui_dynamic_profile_display" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dynamic_profile_display
}

output "gui_dynamic_routing" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_dynamic_routing
}

output "gui_email_collection" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_email_collection
}

output "gui_endpoint_control" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_endpoint_control
}

output "gui_endpoint_control_advanced" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_endpoint_control_advanced
}

output "gui_explicit_proxy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_explicit_proxy
}

output "gui_fortiap_split_tunneling" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_fortiap_split_tunneling
}

output "gui_fortiextender_controller" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_fortiextender_controller
}

output "gui_icap" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_icap
}

output "gui_implicit_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_implicit_policy
}

output "gui_ips" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_ips
}

output "gui_load_balance" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_load_balance
}

output "gui_local_in_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_local_in_policy
}

output "gui_local_reports" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_local_reports
}

output "gui_multicast_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_multicast_policy
}

output "gui_multiple_interface_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_multiple_interface_policy
}

output "gui_multiple_utm_profiles" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_multiple_utm_profiles
}

output "gui_nat46_64" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_nat46_64
}

output "gui_object_colors" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_object_colors
}

output "gui_policy_based_ipsec" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_policy_based_ipsec
}

output "gui_policy_learning" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_policy_learning
}

output "gui_replacement_message_groups" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_replacement_message_groups
}

output "gui_spamfilter" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_spamfilter
}

output "gui_sslvpn_personal_bookmarks" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_sslvpn_personal_bookmarks
}

output "gui_sslvpn_realms" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_sslvpn_realms
}

output "gui_switch_controller" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_switch_controller
}

output "gui_threat_weight" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_threat_weight
}

output "gui_traffic_shaping" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_traffic_shaping
}

output "gui_voip_profile" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_voip_profile
}

output "gui_vpn" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_vpn
}

output "gui_waf_profile" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_waf_profile
}

output "gui_wan_load_balancing" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_wan_load_balancing
}

output "gui_wanopt_cache" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_wanopt_cache
}

output "gui_webfilter" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_webfilter
}

output "gui_webfilter_advanced" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_webfilter_advanced
}

output "gui_wireless_controller" {
  description = "returns a string"
  value       = fortios_system_settings.this.gui_wireless_controller
}

output "http_external_dest" {
  description = "returns a string"
  value       = fortios_system_settings.this.http_external_dest
}

output "id" {
  description = "returns a string"
  value       = fortios_system_settings.this.id
}

output "ike_dn_format" {
  description = "returns a string"
  value       = fortios_system_settings.this.ike_dn_format
}

output "ike_quick_crash_detect" {
  description = "returns a string"
  value       = fortios_system_settings.this.ike_quick_crash_detect
}

output "ike_session_resume" {
  description = "returns a string"
  value       = fortios_system_settings.this.ike_session_resume
}

output "implicit_allow_dns" {
  description = "returns a string"
  value       = fortios_system_settings.this.implicit_allow_dns
}

output "inspection_mode" {
  description = "returns a string"
  value       = fortios_system_settings.this.inspection_mode
}

output "ip" {
  description = "returns a string"
  value       = fortios_system_settings.this.ip
}

output "ip6" {
  description = "returns a string"
  value       = fortios_system_settings.this.ip6
}

output "link_down_access" {
  description = "returns a string"
  value       = fortios_system_settings.this.link_down_access
}

output "lldp_reception" {
  description = "returns a string"
  value       = fortios_system_settings.this.lldp_reception
}

output "lldp_transmission" {
  description = "returns a string"
  value       = fortios_system_settings.this.lldp_transmission
}

output "mac_ttl" {
  description = "returns a number"
  value       = fortios_system_settings.this.mac_ttl
}

output "manageip" {
  description = "returns a string"
  value       = fortios_system_settings.this.manageip
}

output "manageip6" {
  description = "returns a string"
  value       = fortios_system_settings.this.manageip6
}

output "multicast_forward" {
  description = "returns a string"
  value       = fortios_system_settings.this.multicast_forward
}

output "multicast_skip_policy" {
  description = "returns a string"
  value       = fortios_system_settings.this.multicast_skip_policy
}

output "multicast_ttl_notchange" {
  description = "returns a string"
  value       = fortios_system_settings.this.multicast_ttl_notchange
}

output "ngfw_mode" {
  description = "returns a string"
  value       = fortios_system_settings.this.ngfw_mode
}

output "opmode" {
  description = "returns a string"
  value       = fortios_system_settings.this.opmode
}

output "prp_trailer_action" {
  description = "returns a string"
  value       = fortios_system_settings.this.prp_trailer_action
}

output "sccp_port" {
  description = "returns a number"
  value       = fortios_system_settings.this.sccp_port
}

output "ses_denied_traffic" {
  description = "returns a string"
  value       = fortios_system_settings.this.ses_denied_traffic
}

output "sip_helper" {
  description = "returns a string"
  value       = fortios_system_settings.this.sip_helper
}

output "sip_nat_trace" {
  description = "returns a string"
  value       = fortios_system_settings.this.sip_nat_trace
}

output "sip_ssl_port" {
  description = "returns a number"
  value       = fortios_system_settings.this.sip_ssl_port
}

output "sip_tcp_port" {
  description = "returns a number"
  value       = fortios_system_settings.this.sip_tcp_port
}

output "sip_udp_port" {
  description = "returns a number"
  value       = fortios_system_settings.this.sip_udp_port
}

output "snat_hairpin_traffic" {
  description = "returns a string"
  value       = fortios_system_settings.this.snat_hairpin_traffic
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_system_settings.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = fortios_system_settings.this.status
}

output "strict_src_check" {
  description = "returns a string"
  value       = fortios_system_settings.this.strict_src_check
}

output "tcp_session_without_syn" {
  description = "returns a string"
  value       = fortios_system_settings.this.tcp_session_without_syn
}

output "utf8_spam_tagging" {
  description = "returns a string"
  value       = fortios_system_settings.this.utf8_spam_tagging
}

output "v4_ecmp_mode" {
  description = "returns a string"
  value       = fortios_system_settings.this.v4_ecmp_mode
}

output "vpn_stats_log" {
  description = "returns a string"
  value       = fortios_system_settings.this.vpn_stats_log
}

output "vpn_stats_period" {
  description = "returns a number"
  value       = fortios_system_settings.this.vpn_stats_period
}

output "wccp_cache_engine" {
  description = "returns a string"
  value       = fortios_system_settings.this.wccp_cache_engine
}

output "this" {
  value = fortios_system_settings.this
}
```

[top](#index)