# fortios_wirelesscontroller_vap

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontroller_vap" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_vap"

  # access_control_list - (optional) is a type of string
  access_control_list = null
  # acct_interim_interval - (optional) is a type of number
  acct_interim_interval = null
  # additional_akms - (optional) is a type of string
  additional_akms = null
  # address_group - (optional) is a type of string
  address_group = null
  # alias - (optional) is a type of string
  alias = null
  # atf_weight - (optional) is a type of number
  atf_weight = null
  # auth - (optional) is a type of string
  auth = null
  # broadcast_ssid - (optional) is a type of string
  broadcast_ssid = null
  # broadcast_suppression - (optional) is a type of string
  broadcast_suppression = null
  # bss_color_partial - (optional) is a type of string
  bss_color_partial = null
  # captive_portal_ac_name - (optional) is a type of string
  captive_portal_ac_name = null
  # captive_portal_auth_timeout - (optional) is a type of number
  captive_portal_auth_timeout = null
  # captive_portal_macauth_radius_secret - (optional) is a type of string
  captive_portal_macauth_radius_secret = null
  # captive_portal_macauth_radius_server - (optional) is a type of string
  captive_portal_macauth_radius_server = null
  # captive_portal_radius_secret - (optional) is a type of string
  captive_portal_radius_secret = null
  # captive_portal_radius_server - (optional) is a type of string
  captive_portal_radius_server = null
  # captive_portal_session_timeout_interval - (optional) is a type of number
  captive_portal_session_timeout_interval = null
  # dhcp_lease_time - (optional) is a type of number
  dhcp_lease_time = null
  # dhcp_option43_insertion - (optional) is a type of string
  dhcp_option43_insertion = null
  # dhcp_option82_circuit_id_insertion - (optional) is a type of string
  dhcp_option82_circuit_id_insertion = null
  # dhcp_option82_insertion - (optional) is a type of string
  dhcp_option82_insertion = null
  # dhcp_option82_remote_id_insertion - (optional) is a type of string
  dhcp_option82_remote_id_insertion = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # dynamic_vlan - (optional) is a type of string
  dynamic_vlan = null
  # eap_reauth - (optional) is a type of string
  eap_reauth = null
  # eap_reauth_intv - (optional) is a type of number
  eap_reauth_intv = null
  # eapol_key_retries - (optional) is a type of string
  eapol_key_retries = null
  # encrypt - (optional) is a type of string
  encrypt = null
  # external_fast_roaming - (optional) is a type of string
  external_fast_roaming = null
  # external_logout - (optional) is a type of string
  external_logout = null
  # external_web - (optional) is a type of string
  external_web = null
  # external_web_format - (optional) is a type of string
  external_web_format = null
  # fast_bss_transition - (optional) is a type of string
  fast_bss_transition = null
  # fast_roaming - (optional) is a type of string
  fast_roaming = null
  # ft_mobility_domain - (optional) is a type of number
  ft_mobility_domain = null
  # ft_over_ds - (optional) is a type of string
  ft_over_ds = null
  # ft_r0_key_lifetime - (optional) is a type of number
  ft_r0_key_lifetime = null
  # gtk_rekey - (optional) is a type of string
  gtk_rekey = null
  # gtk_rekey_intv - (optional) is a type of number
  gtk_rekey_intv = null
  # high_efficiency - (optional) is a type of string
  high_efficiency = null
  # hotspot20_profile - (optional) is a type of string
  hotspot20_profile = null
  # igmp_snooping - (optional) is a type of string
  igmp_snooping = null
  # intra_vap_privacy - (optional) is a type of string
  intra_vap_privacy = null
  # ip - (optional) is a type of string
  ip = null
  # ipv6_rules - (optional) is a type of string
  ipv6_rules = null
  # key - (optional) is a type of string
  key = null
  # keyindex - (optional) is a type of number
  keyindex = null
  # ldpc - (optional) is a type of string
  ldpc = null
  # local_authentication - (optional) is a type of string
  local_authentication = null
  # local_bridging - (optional) is a type of string
  local_bridging = null
  # local_lan - (optional) is a type of string
  local_lan = null
  # local_standalone - (optional) is a type of string
  local_standalone = null
  # local_standalone_nat - (optional) is a type of string
  local_standalone_nat = null
  # mac_auth_bypass - (optional) is a type of string
  mac_auth_bypass = null
  # mac_filter - (optional) is a type of string
  mac_filter = null
  # mac_filter_policy_other - (optional) is a type of string
  mac_filter_policy_other = null
  # max_clients - (optional) is a type of number
  max_clients = null
  # max_clients_ap - (optional) is a type of number
  max_clients_ap = null
  # me_disable_thresh - (optional) is a type of number
  me_disable_thresh = null
  # mesh_backhaul - (optional) is a type of string
  mesh_backhaul = null
  # mpsk - (optional) is a type of string
  mpsk = null
  # mpsk_concurrent_clients - (optional) is a type of number
  mpsk_concurrent_clients = null
  # mpsk_profile - (optional) is a type of string
  mpsk_profile = null
  # mu_mimo - (optional) is a type of string
  mu_mimo = null
  # multicast_enhance - (optional) is a type of string
  multicast_enhance = null
  # multicast_rate - (optional) is a type of string
  multicast_rate = null
  # name - (required) is a type of string
  name = null
  # okc - (optional) is a type of string
  okc = null
  # owe_groups - (optional) is a type of string
  owe_groups = null
  # owe_transition - (optional) is a type of string
  owe_transition = null
  # owe_transition_ssid - (optional) is a type of string
  owe_transition_ssid = null
  # passphrase - (optional) is a type of string
  passphrase = null
  # pmf - (optional) is a type of string
  pmf = null
  # pmf_assoc_comeback_timeout - (optional) is a type of number
  pmf_assoc_comeback_timeout = null
  # pmf_sa_query_retry_timeout - (optional) is a type of number
  pmf_sa_query_retry_timeout = null
  # port_macauth - (optional) is a type of string
  port_macauth = null
  # port_macauth_reauth_timeout - (optional) is a type of number
  port_macauth_reauth_timeout = null
  # port_macauth_timeout - (optional) is a type of number
  port_macauth_timeout = null
  # portal_message_override_group - (optional) is a type of string
  portal_message_override_group = null
  # portal_type - (optional) is a type of string
  portal_type = null
  # primary_wag_profile - (optional) is a type of string
  primary_wag_profile = null
  # probe_resp_suppression - (optional) is a type of string
  probe_resp_suppression = null
  # probe_resp_threshold - (optional) is a type of string
  probe_resp_threshold = null
  # ptk_rekey - (optional) is a type of string
  ptk_rekey = null
  # ptk_rekey_intv - (optional) is a type of number
  ptk_rekey_intv = null
  # qos_profile - (optional) is a type of string
  qos_profile = null
  # quarantine - (optional) is a type of string
  quarantine = null
  # radio_2g_threshold - (optional) is a type of string
  radio_2g_threshold = null
  # radio_5g_threshold - (optional) is a type of string
  radio_5g_threshold = null
  # radio_sensitivity - (optional) is a type of string
  radio_sensitivity = null
  # radius_mac_auth - (optional) is a type of string
  radius_mac_auth = null
  # radius_mac_auth_server - (optional) is a type of string
  radius_mac_auth_server = null
  # radius_server - (optional) is a type of string
  radius_server = null
  # rates_11a - (optional) is a type of string
  rates_11a = null
  # rates_11ac_ss12 - (optional) is a type of string
  rates_11ac_ss12 = null
  # rates_11ac_ss34 - (optional) is a type of string
  rates_11ac_ss34 = null
  # rates_11bg - (optional) is a type of string
  rates_11bg = null
  # rates_11n_ss12 - (optional) is a type of string
  rates_11n_ss12 = null
  # rates_11n_ss34 - (optional) is a type of string
  rates_11n_ss34 = null
  # sae_groups - (optional) is a type of string
  sae_groups = null
  # sae_password - (optional) is a type of string
  sae_password = null
  # schedule - (optional) is a type of string
  schedule = null
  # secondary_wag_profile - (optional) is a type of string
  secondary_wag_profile = null
  # security - (optional) is a type of string
  security = null
  # security_exempt_list - (optional) is a type of string
  security_exempt_list = null
  # security_obsolete_option - (optional) is a type of string
  security_obsolete_option = null
  # security_redirect_url - (optional) is a type of string
  security_redirect_url = null
  # split_tunneling - (optional) is a type of string
  split_tunneling = null
  # ssid - (optional) is a type of string
  ssid = null
  # sticky_client_remove - (optional) is a type of string
  sticky_client_remove = null
  # sticky_client_threshold_2g - (optional) is a type of string
  sticky_client_threshold_2g = null
  # sticky_client_threshold_5g - (optional) is a type of string
  sticky_client_threshold_5g = null
  # target_wake_time - (optional) is a type of string
  target_wake_time = null
  # tkip_counter_measure - (optional) is a type of string
  tkip_counter_measure = null
  # tunnel_echo_interval - (optional) is a type of number
  tunnel_echo_interval = null
  # tunnel_fallback_interval - (optional) is a type of number
  tunnel_fallback_interval = null
  # utm_profile - (optional) is a type of string
  utm_profile = null
  # vlan_auto - (optional) is a type of string
  vlan_auto = null
  # vlan_pooling - (optional) is a type of string
  vlan_pooling = null
  # vlanid - (optional) is a type of number
  vlanid = null
  # voice_enterprise - (optional) is a type of string
  voice_enterprise = null

  mac_filter_list = [{
    id                = null
    mac               = null
    mac_filter_policy = null
  }]

  mpsk_key = [{
    comment            = null
    concurrent_clients = null
    key_name           = null
    mpsk_schedules = [{
      name = null
    }]
    passphrase = null
  }]

  portal_message_overrides = [{
    auth_disclaimer_page   = null
    auth_login_failed_page = null
    auth_login_page        = null
    auth_reject_page       = null
  }]

  radius_mac_auth_usergroups = [{
    name = null
  }]

  selected_usergroups = [{
    name = null
  }]

  usergroup = [{
    name = null
  }]

  vlan_pool = [{
    id        = null
    wtp_group = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_control_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "acct_interim_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "additional_akms" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "atf_weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "broadcast_ssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "broadcast_suppression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bss_color_partial" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_ac_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_auth_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "captive_portal_macauth_radius_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_macauth_radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_radius_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_session_timeout_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dhcp_lease_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dhcp_option43_insertion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_option82_circuit_id_insertion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_option82_insertion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_option82_remote_id_insertion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap_reauth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap_reauth_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_key_retries" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_fast_roaming" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_logout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_web" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_web_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fast_bss_transition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fast_roaming" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ft_mobility_domain" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ft_over_ds" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ft_r0_key_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gtk_rekey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gtk_rekey_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "high_efficiency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hotspot20_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "igmp_snooping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intra_vap_privacy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_rules" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keyindex" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ldpc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_bridging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_lan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_standalone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_standalone_nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_auth_bypass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_filter_policy_other" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_clients" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_clients_ap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "me_disable_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mesh_backhaul" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mpsk" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mpsk_concurrent_clients" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mpsk_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mu_mimo" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_enhance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_rate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "okc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owe_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owe_transition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owe_transition_ssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pmf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pmf_assoc_comeback_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pmf_sa_query_retry_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_macauth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_macauth_reauth_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_macauth_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "portal_message_override_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "portal_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_wag_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "probe_resp_suppression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "probe_resp_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ptk_rekey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ptk_rekey_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "qos_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quarantine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radio_2g_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radio_5g_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radio_sensitivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_mac_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_mac_auth_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rates_11a" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rates_11ac_ss12" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rates_11ac_ss34" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rates_11bg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rates_11n_ss12" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rates_11n_ss34" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sae_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sae_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_wag_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_exempt_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_obsolete_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_redirect_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "split_tunneling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sticky_client_remove" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sticky_client_threshold_2g" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sticky_client_threshold_5g" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_wake_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tkip_counter_measure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_echo_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel_fallback_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "utm_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_auto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_pooling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlanid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "voice_enterprise" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_filter_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id                = number
      mac               = string
      mac_filter_policy = string
    }
  ))
  default = []
}

variable "mpsk_key" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment            = string
      concurrent_clients = string
      key_name           = string
      mpsk_schedules = list(object(
        {
          name = string
        }
      ))
      passphrase = string
    }
  ))
  default = []
}

variable "portal_message_overrides" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_disclaimer_page   = string
      auth_login_failed_page = string
      auth_login_page        = string
      auth_reject_page       = string
    }
  ))
  default = []
}

variable "radius_mac_auth_usergroups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "selected_usergroups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "usergroup" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "vlan_pool" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id        = number
      wtp_group = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_vap" "this" {
  access_control_list                     = var.access_control_list
  acct_interim_interval                   = var.acct_interim_interval
  additional_akms                         = var.additional_akms
  address_group                           = var.address_group
  alias                                   = var.alias
  atf_weight                              = var.atf_weight
  auth                                    = var.auth
  broadcast_ssid                          = var.broadcast_ssid
  broadcast_suppression                   = var.broadcast_suppression
  bss_color_partial                       = var.bss_color_partial
  captive_portal_ac_name                  = var.captive_portal_ac_name
  captive_portal_auth_timeout             = var.captive_portal_auth_timeout
  captive_portal_macauth_radius_secret    = var.captive_portal_macauth_radius_secret
  captive_portal_macauth_radius_server    = var.captive_portal_macauth_radius_server
  captive_portal_radius_secret            = var.captive_portal_radius_secret
  captive_portal_radius_server            = var.captive_portal_radius_server
  captive_portal_session_timeout_interval = var.captive_portal_session_timeout_interval
  dhcp_lease_time                         = var.dhcp_lease_time
  dhcp_option43_insertion                 = var.dhcp_option43_insertion
  dhcp_option82_circuit_id_insertion      = var.dhcp_option82_circuit_id_insertion
  dhcp_option82_insertion                 = var.dhcp_option82_insertion
  dhcp_option82_remote_id_insertion       = var.dhcp_option82_remote_id_insertion
  dynamic_sort_subtable                   = var.dynamic_sort_subtable
  dynamic_vlan                            = var.dynamic_vlan
  eap_reauth                              = var.eap_reauth
  eap_reauth_intv                         = var.eap_reauth_intv
  eapol_key_retries                       = var.eapol_key_retries
  encrypt                                 = var.encrypt
  external_fast_roaming                   = var.external_fast_roaming
  external_logout                         = var.external_logout
  external_web                            = var.external_web
  external_web_format                     = var.external_web_format
  fast_bss_transition                     = var.fast_bss_transition
  fast_roaming                            = var.fast_roaming
  ft_mobility_domain                      = var.ft_mobility_domain
  ft_over_ds                              = var.ft_over_ds
  ft_r0_key_lifetime                      = var.ft_r0_key_lifetime
  gtk_rekey                               = var.gtk_rekey
  gtk_rekey_intv                          = var.gtk_rekey_intv
  high_efficiency                         = var.high_efficiency
  hotspot20_profile                       = var.hotspot20_profile
  igmp_snooping                           = var.igmp_snooping
  intra_vap_privacy                       = var.intra_vap_privacy
  ip                                      = var.ip
  ipv6_rules                              = var.ipv6_rules
  key                                     = var.key
  keyindex                                = var.keyindex
  ldpc                                    = var.ldpc
  local_authentication                    = var.local_authentication
  local_bridging                          = var.local_bridging
  local_lan                               = var.local_lan
  local_standalone                        = var.local_standalone
  local_standalone_nat                    = var.local_standalone_nat
  mac_auth_bypass                         = var.mac_auth_bypass
  mac_filter                              = var.mac_filter
  mac_filter_policy_other                 = var.mac_filter_policy_other
  max_clients                             = var.max_clients
  max_clients_ap                          = var.max_clients_ap
  me_disable_thresh                       = var.me_disable_thresh
  mesh_backhaul                           = var.mesh_backhaul
  mpsk                                    = var.mpsk
  mpsk_concurrent_clients                 = var.mpsk_concurrent_clients
  mpsk_profile                            = var.mpsk_profile
  mu_mimo                                 = var.mu_mimo
  multicast_enhance                       = var.multicast_enhance
  multicast_rate                          = var.multicast_rate
  name                                    = var.name
  okc                                     = var.okc
  owe_groups                              = var.owe_groups
  owe_transition                          = var.owe_transition
  owe_transition_ssid                     = var.owe_transition_ssid
  passphrase                              = var.passphrase
  pmf                                     = var.pmf
  pmf_assoc_comeback_timeout              = var.pmf_assoc_comeback_timeout
  pmf_sa_query_retry_timeout              = var.pmf_sa_query_retry_timeout
  port_macauth                            = var.port_macauth
  port_macauth_reauth_timeout             = var.port_macauth_reauth_timeout
  port_macauth_timeout                    = var.port_macauth_timeout
  portal_message_override_group           = var.portal_message_override_group
  portal_type                             = var.portal_type
  primary_wag_profile                     = var.primary_wag_profile
  probe_resp_suppression                  = var.probe_resp_suppression
  probe_resp_threshold                    = var.probe_resp_threshold
  ptk_rekey                               = var.ptk_rekey
  ptk_rekey_intv                          = var.ptk_rekey_intv
  qos_profile                             = var.qos_profile
  quarantine                              = var.quarantine
  radio_2g_threshold                      = var.radio_2g_threshold
  radio_5g_threshold                      = var.radio_5g_threshold
  radio_sensitivity                       = var.radio_sensitivity
  radius_mac_auth                         = var.radius_mac_auth
  radius_mac_auth_server                  = var.radius_mac_auth_server
  radius_server                           = var.radius_server
  rates_11a                               = var.rates_11a
  rates_11ac_ss12                         = var.rates_11ac_ss12
  rates_11ac_ss34                         = var.rates_11ac_ss34
  rates_11bg                              = var.rates_11bg
  rates_11n_ss12                          = var.rates_11n_ss12
  rates_11n_ss34                          = var.rates_11n_ss34
  sae_groups                              = var.sae_groups
  sae_password                            = var.sae_password
  schedule                                = var.schedule
  secondary_wag_profile                   = var.secondary_wag_profile
  security                                = var.security
  security_exempt_list                    = var.security_exempt_list
  security_obsolete_option                = var.security_obsolete_option
  security_redirect_url                   = var.security_redirect_url
  split_tunneling                         = var.split_tunneling
  ssid                                    = var.ssid
  sticky_client_remove                    = var.sticky_client_remove
  sticky_client_threshold_2g              = var.sticky_client_threshold_2g
  sticky_client_threshold_5g              = var.sticky_client_threshold_5g
  target_wake_time                        = var.target_wake_time
  tkip_counter_measure                    = var.tkip_counter_measure
  tunnel_echo_interval                    = var.tunnel_echo_interval
  tunnel_fallback_interval                = var.tunnel_fallback_interval
  utm_profile                             = var.utm_profile
  vlan_auto                               = var.vlan_auto
  vlan_pooling                            = var.vlan_pooling
  vlanid                                  = var.vlanid
  voice_enterprise                        = var.voice_enterprise

  dynamic "mac_filter_list" {
    for_each = var.mac_filter_list
    content {
      id                = mac_filter_list.value["id"]
      mac               = mac_filter_list.value["mac"]
      mac_filter_policy = mac_filter_list.value["mac_filter_policy"]
    }
  }

  dynamic "mpsk_key" {
    for_each = var.mpsk_key
    content {
      comment            = mpsk_key.value["comment"]
      concurrent_clients = mpsk_key.value["concurrent_clients"]
      key_name           = mpsk_key.value["key_name"]
      passphrase         = mpsk_key.value["passphrase"]

      dynamic "mpsk_schedules" {
        for_each = mpsk_key.value.mpsk_schedules
        content {
          name = mpsk_schedules.value["name"]
        }
      }

    }
  }

  dynamic "portal_message_overrides" {
    for_each = var.portal_message_overrides
    content {
      auth_disclaimer_page   = portal_message_overrides.value["auth_disclaimer_page"]
      auth_login_failed_page = portal_message_overrides.value["auth_login_failed_page"]
      auth_login_page        = portal_message_overrides.value["auth_login_page"]
      auth_reject_page       = portal_message_overrides.value["auth_reject_page"]
    }
  }

  dynamic "radius_mac_auth_usergroups" {
    for_each = var.radius_mac_auth_usergroups
    content {
      name = radius_mac_auth_usergroups.value["name"]
    }
  }

  dynamic "selected_usergroups" {
    for_each = var.selected_usergroups
    content {
      name = selected_usergroups.value["name"]
    }
  }

  dynamic "usergroup" {
    for_each = var.usergroup
    content {
      name = usergroup.value["name"]
    }
  }

  dynamic "vlan_pool" {
    for_each = var.vlan_pool
    content {
      id        = vlan_pool.value["id"]
      wtp_group = vlan_pool.value["wtp_group"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_control_list" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.access_control_list
}

output "acct_interim_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.acct_interim_interval
}

output "additional_akms" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.additional_akms
}

output "address_group" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.address_group
}

output "alias" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.alias
}

output "atf_weight" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.atf_weight
}

output "auth" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.auth
}

output "broadcast_ssid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.broadcast_ssid
}

output "broadcast_suppression" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.broadcast_suppression
}

output "bss_color_partial" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.bss_color_partial
}

output "captive_portal_ac_name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.captive_portal_ac_name
}

output "captive_portal_auth_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.captive_portal_auth_timeout
}

output "captive_portal_macauth_radius_server" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.captive_portal_macauth_radius_server
}

output "captive_portal_radius_server" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.captive_portal_radius_server
}

output "captive_portal_session_timeout_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.captive_portal_session_timeout_interval
}

output "dhcp_lease_time" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.dhcp_lease_time
}

output "dhcp_option43_insertion" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.dhcp_option43_insertion
}

output "dhcp_option82_circuit_id_insertion" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.dhcp_option82_circuit_id_insertion
}

output "dhcp_option82_insertion" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.dhcp_option82_insertion
}

output "dhcp_option82_remote_id_insertion" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.dhcp_option82_remote_id_insertion
}

output "dynamic_vlan" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.dynamic_vlan
}

output "eap_reauth" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.eap_reauth
}

output "eap_reauth_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.eap_reauth_intv
}

output "eapol_key_retries" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.eapol_key_retries
}

output "encrypt" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.encrypt
}

output "external_fast_roaming" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.external_fast_roaming
}

output "external_logout" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.external_logout
}

output "external_web" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.external_web
}

output "external_web_format" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.external_web_format
}

output "fast_bss_transition" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.fast_bss_transition
}

output "fast_roaming" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.fast_roaming
}

output "ft_mobility_domain" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.ft_mobility_domain
}

output "ft_over_ds" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.ft_over_ds
}

output "ft_r0_key_lifetime" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.ft_r0_key_lifetime
}

output "gtk_rekey" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.gtk_rekey
}

output "gtk_rekey_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.gtk_rekey_intv
}

output "high_efficiency" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.high_efficiency
}

output "hotspot20_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.hotspot20_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.id
}

output "igmp_snooping" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.igmp_snooping
}

output "intra_vap_privacy" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.intra_vap_privacy
}

output "ip" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.ip
}

output "ipv6_rules" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.ipv6_rules
}

output "keyindex" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.keyindex
}

output "ldpc" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.ldpc
}

output "local_authentication" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.local_authentication
}

output "local_bridging" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.local_bridging
}

output "local_lan" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.local_lan
}

output "local_standalone" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.local_standalone
}

output "local_standalone_nat" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.local_standalone_nat
}

output "mac_auth_bypass" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mac_auth_bypass
}

output "mac_filter" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mac_filter
}

output "mac_filter_policy_other" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mac_filter_policy_other
}

output "max_clients" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.max_clients
}

output "max_clients_ap" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.max_clients_ap
}

output "me_disable_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.me_disable_thresh
}

output "mesh_backhaul" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mesh_backhaul
}

output "mpsk" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mpsk
}

output "mpsk_concurrent_clients" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.mpsk_concurrent_clients
}

output "mpsk_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mpsk_profile
}

output "mu_mimo" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.mu_mimo
}

output "multicast_enhance" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.multicast_enhance
}

output "multicast_rate" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.multicast_rate
}

output "okc" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.okc
}

output "owe_groups" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.owe_groups
}

output "owe_transition" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.owe_transition
}

output "owe_transition_ssid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.owe_transition_ssid
}

output "pmf" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.pmf
}

output "pmf_assoc_comeback_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.pmf_assoc_comeback_timeout
}

output "pmf_sa_query_retry_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.pmf_sa_query_retry_timeout
}

output "port_macauth" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.port_macauth
}

output "port_macauth_reauth_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.port_macauth_reauth_timeout
}

output "port_macauth_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.port_macauth_timeout
}

output "portal_message_override_group" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.portal_message_override_group
}

output "portal_type" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.portal_type
}

output "primary_wag_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.primary_wag_profile
}

output "probe_resp_suppression" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.probe_resp_suppression
}

output "probe_resp_threshold" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.probe_resp_threshold
}

output "ptk_rekey" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.ptk_rekey
}

output "ptk_rekey_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.ptk_rekey_intv
}

output "qos_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.qos_profile
}

output "quarantine" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.quarantine
}

output "radio_2g_threshold" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.radio_2g_threshold
}

output "radio_5g_threshold" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.radio_5g_threshold
}

output "radio_sensitivity" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.radio_sensitivity
}

output "radius_mac_auth" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.radius_mac_auth
}

output "radius_mac_auth_server" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.radius_mac_auth_server
}

output "radius_server" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.radius_server
}

output "rates_11a" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.rates_11a
}

output "rates_11ac_ss12" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.rates_11ac_ss12
}

output "rates_11ac_ss34" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.rates_11ac_ss34
}

output "rates_11bg" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.rates_11bg
}

output "rates_11n_ss12" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.rates_11n_ss12
}

output "rates_11n_ss34" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.rates_11n_ss34
}

output "sae_groups" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.sae_groups
}

output "schedule" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.schedule
}

output "secondary_wag_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.secondary_wag_profile
}

output "security" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.security
}

output "security_exempt_list" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.security_exempt_list
}

output "security_obsolete_option" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.security_obsolete_option
}

output "security_redirect_url" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.security_redirect_url
}

output "split_tunneling" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.split_tunneling
}

output "ssid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.ssid
}

output "sticky_client_remove" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.sticky_client_remove
}

output "sticky_client_threshold_2g" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.sticky_client_threshold_2g
}

output "sticky_client_threshold_5g" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.sticky_client_threshold_5g
}

output "target_wake_time" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.target_wake_time
}

output "tkip_counter_measure" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.tkip_counter_measure
}

output "tunnel_echo_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.tunnel_echo_interval
}

output "tunnel_fallback_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.tunnel_fallback_interval
}

output "utm_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.utm_profile
}

output "vlan_auto" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.vlan_auto
}

output "vlan_pooling" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.vlan_pooling
}

output "vlanid" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_vap.this.vlanid
}

output "voice_enterprise" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vap.this.voice_enterprise
}

output "this" {
  value = fortios_wirelesscontroller_vap.this
}
```

[top](#index)