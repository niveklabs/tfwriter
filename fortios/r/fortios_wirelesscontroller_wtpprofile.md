# fortios_wirelesscontroller_wtpprofile

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
module "fortios_wirelesscontroller_wtpprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_wtpprofile"

  # allowaccess - (optional) is a type of string
  allowaccess = null
  # ap_country - (optional) is a type of string
  ap_country = null
  # ap_handoff - (optional) is a type of string
  ap_handoff = null
  # apcfg_profile - (optional) is a type of string
  apcfg_profile = null
  # ble_profile - (optional) is a type of string
  ble_profile = null
  # comment - (optional) is a type of string
  comment = null
  # control_message_offload - (optional) is a type of string
  control_message_offload = null
  # dtls_in_kernel - (optional) is a type of string
  dtls_in_kernel = null
  # dtls_policy - (optional) is a type of string
  dtls_policy = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # energy_efficient_ethernet - (optional) is a type of string
  energy_efficient_ethernet = null
  # ext_info_enable - (optional) is a type of string
  ext_info_enable = null
  # frequency_handoff - (optional) is a type of string
  frequency_handoff = null
  # handoff_roaming - (optional) is a type of string
  handoff_roaming = null
  # handoff_rssi - (optional) is a type of number
  handoff_rssi = null
  # handoff_sta_thresh - (optional) is a type of number
  handoff_sta_thresh = null
  # ip_fragment_preventing - (optional) is a type of string
  ip_fragment_preventing = null
  # led_state - (optional) is a type of string
  led_state = null
  # lldp - (optional) is a type of string
  lldp = null
  # login_passwd - (optional) is a type of string
  login_passwd = null
  # login_passwd_change - (optional) is a type of string
  login_passwd_change = null
  # max_clients - (optional) is a type of number
  max_clients = null
  # name - (optional) is a type of string
  name = null
  # poe_mode - (optional) is a type of string
  poe_mode = null
  # split_tunneling_acl_local_ap_subnet - (optional) is a type of string
  split_tunneling_acl_local_ap_subnet = null
  # split_tunneling_acl_path - (optional) is a type of string
  split_tunneling_acl_path = null
  # tun_mtu_downlink - (optional) is a type of number
  tun_mtu_downlink = null
  # tun_mtu_uplink - (optional) is a type of number
  tun_mtu_uplink = null
  # wan_port_mode - (optional) is a type of string
  wan_port_mode = null

  deny_mac_list = [{
    id  = null
    mac = null
  }]

  lan = [{
    port1_mode    = null
    port1_ssid    = null
    port2_mode    = null
    port2_ssid    = null
    port3_mode    = null
    port3_ssid    = null
    port4_mode    = null
    port4_ssid    = null
    port5_mode    = null
    port5_ssid    = null
    port6_mode    = null
    port6_ssid    = null
    port7_mode    = null
    port7_ssid    = null
    port8_mode    = null
    port8_ssid    = null
    port_esl_mode = null
    port_esl_ssid = null
    port_mode     = null
    port_ssid     = null
  }]

  lbs = [{
    aeroscout               = null
    aeroscout_ap_mac        = null
    aeroscout_mmu_report    = null
    aeroscout_mu            = null
    aeroscout_mu_factor     = null
    aeroscout_mu_timeout    = null
    aeroscout_server_ip     = null
    aeroscout_server_port   = null
    ekahau_blink_mode       = null
    ekahau_tag              = null
    erc_server_ip           = null
    erc_server_port         = null
    fortipresence           = null
    fortipresence_ble       = null
    fortipresence_frequency = null
    fortipresence_port      = null
    fortipresence_project   = null
    fortipresence_rogue     = null
    fortipresence_secret    = null
    fortipresence_server    = null
    fortipresence_unassoc   = null
    station_locate          = null
  }]

  led_schedules = [{
    name = null
  }]

  platform = [{
    ddscan = null
    mode   = null
    type   = null
  }]

  radio_1 = [{
    airtime_fairness            = null
    amsdu                       = null
    ap_handoff                  = null
    ap_sniffer_addr             = null
    ap_sniffer_bufsize          = null
    ap_sniffer_chan             = null
    ap_sniffer_ctl              = null
    ap_sniffer_data             = null
    ap_sniffer_mgmt_beacon      = null
    ap_sniffer_mgmt_other       = null
    ap_sniffer_mgmt_probe       = null
    auto_power_high             = null
    auto_power_level            = null
    auto_power_low              = null
    auto_power_target           = null
    band                        = null
    band_5g_type                = null
    bandwidth_admission_control = null
    bandwidth_capacity          = null
    beacon_interval             = null
    bss_color                   = null
    call_admission_control      = null
    call_capacity               = null
    channel = [{
      chan = null
    }]
    channel_bonding      = null
    channel_utilization  = null
    coexistence          = null
    darrp                = null
    drma                 = null
    drma_sensitivity     = null
    dtim                 = null
    frag_threshold       = null
    frequency_handoff    = null
    max_clients          = null
    max_distance         = null
    mode                 = null
    power_level          = null
    powersave_optimize   = null
    protection_mode      = null
    radio_id             = null
    rts_threshold        = null
    short_guard_interval = null
    spectrum_analysis    = null
    transmit_optimize    = null
    vap_all              = null
    vaps = [{
      name = null
    }]
    wids_profile  = null
    zero_wait_dfs = null
  }]

  radio_2 = [{
    airtime_fairness            = null
    amsdu                       = null
    ap_handoff                  = null
    ap_sniffer_addr             = null
    ap_sniffer_bufsize          = null
    ap_sniffer_chan             = null
    ap_sniffer_ctl              = null
    ap_sniffer_data             = null
    ap_sniffer_mgmt_beacon      = null
    ap_sniffer_mgmt_other       = null
    ap_sniffer_mgmt_probe       = null
    auto_power_high             = null
    auto_power_level            = null
    auto_power_low              = null
    auto_power_target           = null
    band                        = null
    band_5g_type                = null
    bandwidth_admission_control = null
    bandwidth_capacity          = null
    beacon_interval             = null
    bss_color                   = null
    call_admission_control      = null
    call_capacity               = null
    channel = [{
      chan = null
    }]
    channel_bonding      = null
    channel_utilization  = null
    coexistence          = null
    darrp                = null
    drma                 = null
    drma_sensitivity     = null
    dtim                 = null
    frag_threshold       = null
    frequency_handoff    = null
    max_clients          = null
    max_distance         = null
    mode                 = null
    power_level          = null
    powersave_optimize   = null
    protection_mode      = null
    radio_id             = null
    rts_threshold        = null
    short_guard_interval = null
    spectrum_analysis    = null
    transmit_optimize    = null
    vap_all              = null
    vaps = [{
      name = null
    }]
    wids_profile  = null
    zero_wait_dfs = null
  }]

  radio_3 = [{
    airtime_fairness            = null
    amsdu                       = null
    ap_handoff                  = null
    ap_sniffer_addr             = null
    ap_sniffer_bufsize          = null
    ap_sniffer_chan             = null
    ap_sniffer_ctl              = null
    ap_sniffer_data             = null
    ap_sniffer_mgmt_beacon      = null
    ap_sniffer_mgmt_other       = null
    ap_sniffer_mgmt_probe       = null
    auto_power_high             = null
    auto_power_level            = null
    auto_power_low              = null
    auto_power_target           = null
    band                        = null
    band_5g_type                = null
    bandwidth_admission_control = null
    bandwidth_capacity          = null
    beacon_interval             = null
    bss_color                   = null
    call_admission_control      = null
    call_capacity               = null
    channel = [{
      chan = null
    }]
    channel_bonding      = null
    channel_utilization  = null
    coexistence          = null
    darrp                = null
    drma                 = null
    drma_sensitivity     = null
    dtim                 = null
    frag_threshold       = null
    frequency_handoff    = null
    max_clients          = null
    max_distance         = null
    mode                 = null
    power_level          = null
    powersave_optimize   = null
    protection_mode      = null
    rts_threshold        = null
    short_guard_interval = null
    spectrum_analysis    = null
    transmit_optimize    = null
    vap_all              = null
    vaps = [{
      name = null
    }]
    wids_profile  = null
    zero_wait_dfs = null
  }]

  radio_4 = [{
    airtime_fairness            = null
    amsdu                       = null
    ap_handoff                  = null
    ap_sniffer_addr             = null
    ap_sniffer_bufsize          = null
    ap_sniffer_chan             = null
    ap_sniffer_ctl              = null
    ap_sniffer_data             = null
    ap_sniffer_mgmt_beacon      = null
    ap_sniffer_mgmt_other       = null
    ap_sniffer_mgmt_probe       = null
    auto_power_high             = null
    auto_power_level            = null
    auto_power_low              = null
    auto_power_target           = null
    band                        = null
    band_5g_type                = null
    bandwidth_admission_control = null
    bandwidth_capacity          = null
    beacon_interval             = null
    bss_color                   = null
    call_admission_control      = null
    call_capacity               = null
    channel = [{
      chan = null
    }]
    channel_bonding      = null
    channel_utilization  = null
    coexistence          = null
    darrp                = null
    drma                 = null
    drma_sensitivity     = null
    dtim                 = null
    frag_threshold       = null
    frequency_handoff    = null
    max_clients          = null
    max_distance         = null
    mode                 = null
    power_level          = null
    powersave_optimize   = null
    protection_mode      = null
    rts_threshold        = null
    short_guard_interval = null
    spectrum_analysis    = null
    transmit_optimize    = null
    vap_all              = null
    vaps = [{
      name = null
    }]
    wids_profile  = null
    zero_wait_dfs = null
  }]

  split_tunneling_acl = [{
    dest_ip = null
    id      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_country" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_handoff" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "apcfg_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ble_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "control_message_offload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dtls_in_kernel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dtls_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "energy_efficient_ethernet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ext_info_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frequency_handoff" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "handoff_roaming" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "handoff_rssi" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "handoff_sta_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_fragment_preventing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "led_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_passwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_passwd_change" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_clients" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "poe_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "split_tunneling_acl_local_ap_subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "split_tunneling_acl_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tun_mtu_downlink" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tun_mtu_uplink" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wan_port_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deny_mac_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id  = number
      mac = string
    }
  ))
  default = []
}

variable "lan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      port1_mode    = string
      port1_ssid    = string
      port2_mode    = string
      port2_ssid    = string
      port3_mode    = string
      port3_ssid    = string
      port4_mode    = string
      port4_ssid    = string
      port5_mode    = string
      port5_ssid    = string
      port6_mode    = string
      port6_ssid    = string
      port7_mode    = string
      port7_ssid    = string
      port8_mode    = string
      port8_ssid    = string
      port_esl_mode = string
      port_esl_ssid = string
      port_mode     = string
      port_ssid     = string
    }
  ))
  default = []
}

variable "lbs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aeroscout               = string
      aeroscout_ap_mac        = string
      aeroscout_mmu_report    = string
      aeroscout_mu            = string
      aeroscout_mu_factor     = number
      aeroscout_mu_timeout    = number
      aeroscout_server_ip     = string
      aeroscout_server_port   = number
      ekahau_blink_mode       = string
      ekahau_tag              = string
      erc_server_ip           = string
      erc_server_port         = number
      fortipresence           = string
      fortipresence_ble       = string
      fortipresence_frequency = number
      fortipresence_port      = number
      fortipresence_project   = string
      fortipresence_rogue     = string
      fortipresence_secret    = string
      fortipresence_server    = string
      fortipresence_unassoc   = string
      station_locate          = string
    }
  ))
  default = []
}

variable "led_schedules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "platform" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ddscan = string
      mode   = string
      type   = string
    }
  ))
  default = []
}

variable "radio_1" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      airtime_fairness            = string
      amsdu                       = string
      ap_handoff                  = string
      ap_sniffer_addr             = string
      ap_sniffer_bufsize          = number
      ap_sniffer_chan             = number
      ap_sniffer_ctl              = string
      ap_sniffer_data             = string
      ap_sniffer_mgmt_beacon      = string
      ap_sniffer_mgmt_other       = string
      ap_sniffer_mgmt_probe       = string
      auto_power_high             = number
      auto_power_level            = string
      auto_power_low              = number
      auto_power_target           = string
      band                        = string
      band_5g_type                = string
      bandwidth_admission_control = string
      bandwidth_capacity          = number
      beacon_interval             = number
      bss_color                   = number
      call_admission_control      = string
      call_capacity               = number
      channel = list(object(
        {
          chan = string
        }
      ))
      channel_bonding      = string
      channel_utilization  = string
      coexistence          = string
      darrp                = string
      drma                 = string
      drma_sensitivity     = string
      dtim                 = number
      frag_threshold       = number
      frequency_handoff    = string
      max_clients          = number
      max_distance         = number
      mode                 = string
      power_level          = number
      powersave_optimize   = string
      protection_mode      = string
      radio_id             = number
      rts_threshold        = number
      short_guard_interval = string
      spectrum_analysis    = string
      transmit_optimize    = string
      vap_all              = string
      vaps = list(object(
        {
          name = string
        }
      ))
      wids_profile  = string
      zero_wait_dfs = string
    }
  ))
  default = []
}

variable "radio_2" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      airtime_fairness            = string
      amsdu                       = string
      ap_handoff                  = string
      ap_sniffer_addr             = string
      ap_sniffer_bufsize          = number
      ap_sniffer_chan             = number
      ap_sniffer_ctl              = string
      ap_sniffer_data             = string
      ap_sniffer_mgmt_beacon      = string
      ap_sniffer_mgmt_other       = string
      ap_sniffer_mgmt_probe       = string
      auto_power_high             = number
      auto_power_level            = string
      auto_power_low              = number
      auto_power_target           = string
      band                        = string
      band_5g_type                = string
      bandwidth_admission_control = string
      bandwidth_capacity          = number
      beacon_interval             = number
      bss_color                   = number
      call_admission_control      = string
      call_capacity               = number
      channel = list(object(
        {
          chan = string
        }
      ))
      channel_bonding      = string
      channel_utilization  = string
      coexistence          = string
      darrp                = string
      drma                 = string
      drma_sensitivity     = string
      dtim                 = number
      frag_threshold       = number
      frequency_handoff    = string
      max_clients          = number
      max_distance         = number
      mode                 = string
      power_level          = number
      powersave_optimize   = string
      protection_mode      = string
      radio_id             = number
      rts_threshold        = number
      short_guard_interval = string
      spectrum_analysis    = string
      transmit_optimize    = string
      vap_all              = string
      vaps = list(object(
        {
          name = string
        }
      ))
      wids_profile  = string
      zero_wait_dfs = string
    }
  ))
  default = []
}

variable "radio_3" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      airtime_fairness            = string
      amsdu                       = string
      ap_handoff                  = string
      ap_sniffer_addr             = string
      ap_sniffer_bufsize          = number
      ap_sniffer_chan             = number
      ap_sniffer_ctl              = string
      ap_sniffer_data             = string
      ap_sniffer_mgmt_beacon      = string
      ap_sniffer_mgmt_other       = string
      ap_sniffer_mgmt_probe       = string
      auto_power_high             = number
      auto_power_level            = string
      auto_power_low              = number
      auto_power_target           = string
      band                        = string
      band_5g_type                = string
      bandwidth_admission_control = string
      bandwidth_capacity          = number
      beacon_interval             = number
      bss_color                   = number
      call_admission_control      = string
      call_capacity               = number
      channel = list(object(
        {
          chan = string
        }
      ))
      channel_bonding      = string
      channel_utilization  = string
      coexistence          = string
      darrp                = string
      drma                 = string
      drma_sensitivity     = string
      dtim                 = number
      frag_threshold       = number
      frequency_handoff    = string
      max_clients          = number
      max_distance         = number
      mode                 = string
      power_level          = number
      powersave_optimize   = string
      protection_mode      = string
      rts_threshold        = number
      short_guard_interval = string
      spectrum_analysis    = string
      transmit_optimize    = string
      vap_all              = string
      vaps = list(object(
        {
          name = string
        }
      ))
      wids_profile  = string
      zero_wait_dfs = string
    }
  ))
  default = []
}

variable "radio_4" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      airtime_fairness            = string
      amsdu                       = string
      ap_handoff                  = string
      ap_sniffer_addr             = string
      ap_sniffer_bufsize          = number
      ap_sniffer_chan             = number
      ap_sniffer_ctl              = string
      ap_sniffer_data             = string
      ap_sniffer_mgmt_beacon      = string
      ap_sniffer_mgmt_other       = string
      ap_sniffer_mgmt_probe       = string
      auto_power_high             = number
      auto_power_level            = string
      auto_power_low              = number
      auto_power_target           = string
      band                        = string
      band_5g_type                = string
      bandwidth_admission_control = string
      bandwidth_capacity          = number
      beacon_interval             = number
      bss_color                   = number
      call_admission_control      = string
      call_capacity               = number
      channel = list(object(
        {
          chan = string
        }
      ))
      channel_bonding      = string
      channel_utilization  = string
      coexistence          = string
      darrp                = string
      drma                 = string
      drma_sensitivity     = string
      dtim                 = number
      frag_threshold       = number
      frequency_handoff    = string
      max_clients          = number
      max_distance         = number
      mode                 = string
      power_level          = number
      powersave_optimize   = string
      protection_mode      = string
      rts_threshold        = number
      short_guard_interval = string
      spectrum_analysis    = string
      transmit_optimize    = string
      vap_all              = string
      vaps = list(object(
        {
          name = string
        }
      ))
      wids_profile  = string
      zero_wait_dfs = string
    }
  ))
  default = []
}

variable "split_tunneling_acl" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dest_ip = string
      id      = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_wtpprofile" "this" {
  # allowaccess - (optional) is a type of string
  allowaccess = var.allowaccess
  # ap_country - (optional) is a type of string
  ap_country = var.ap_country
  # ap_handoff - (optional) is a type of string
  ap_handoff = var.ap_handoff
  # apcfg_profile - (optional) is a type of string
  apcfg_profile = var.apcfg_profile
  # ble_profile - (optional) is a type of string
  ble_profile = var.ble_profile
  # comment - (optional) is a type of string
  comment = var.comment
  # control_message_offload - (optional) is a type of string
  control_message_offload = var.control_message_offload
  # dtls_in_kernel - (optional) is a type of string
  dtls_in_kernel = var.dtls_in_kernel
  # dtls_policy - (optional) is a type of string
  dtls_policy = var.dtls_policy
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # energy_efficient_ethernet - (optional) is a type of string
  energy_efficient_ethernet = var.energy_efficient_ethernet
  # ext_info_enable - (optional) is a type of string
  ext_info_enable = var.ext_info_enable
  # frequency_handoff - (optional) is a type of string
  frequency_handoff = var.frequency_handoff
  # handoff_roaming - (optional) is a type of string
  handoff_roaming = var.handoff_roaming
  # handoff_rssi - (optional) is a type of number
  handoff_rssi = var.handoff_rssi
  # handoff_sta_thresh - (optional) is a type of number
  handoff_sta_thresh = var.handoff_sta_thresh
  # ip_fragment_preventing - (optional) is a type of string
  ip_fragment_preventing = var.ip_fragment_preventing
  # led_state - (optional) is a type of string
  led_state = var.led_state
  # lldp - (optional) is a type of string
  lldp = var.lldp
  # login_passwd - (optional) is a type of string
  login_passwd = var.login_passwd
  # login_passwd_change - (optional) is a type of string
  login_passwd_change = var.login_passwd_change
  # max_clients - (optional) is a type of number
  max_clients = var.max_clients
  # name - (optional) is a type of string
  name = var.name
  # poe_mode - (optional) is a type of string
  poe_mode = var.poe_mode
  # split_tunneling_acl_local_ap_subnet - (optional) is a type of string
  split_tunneling_acl_local_ap_subnet = var.split_tunneling_acl_local_ap_subnet
  # split_tunneling_acl_path - (optional) is a type of string
  split_tunneling_acl_path = var.split_tunneling_acl_path
  # tun_mtu_downlink - (optional) is a type of number
  tun_mtu_downlink = var.tun_mtu_downlink
  # tun_mtu_uplink - (optional) is a type of number
  tun_mtu_uplink = var.tun_mtu_uplink
  # wan_port_mode - (optional) is a type of string
  wan_port_mode = var.wan_port_mode

  dynamic "deny_mac_list" {
    for_each = var.deny_mac_list
    content {
      # id - (optional) is a type of number
      id = deny_mac_list.value["id"]
      # mac - (optional) is a type of string
      mac = deny_mac_list.value["mac"]
    }
  }

  dynamic "lan" {
    for_each = var.lan
    content {
      # port1_mode - (optional) is a type of string
      port1_mode = lan.value["port1_mode"]
      # port1_ssid - (optional) is a type of string
      port1_ssid = lan.value["port1_ssid"]
      # port2_mode - (optional) is a type of string
      port2_mode = lan.value["port2_mode"]
      # port2_ssid - (optional) is a type of string
      port2_ssid = lan.value["port2_ssid"]
      # port3_mode - (optional) is a type of string
      port3_mode = lan.value["port3_mode"]
      # port3_ssid - (optional) is a type of string
      port3_ssid = lan.value["port3_ssid"]
      # port4_mode - (optional) is a type of string
      port4_mode = lan.value["port4_mode"]
      # port4_ssid - (optional) is a type of string
      port4_ssid = lan.value["port4_ssid"]
      # port5_mode - (optional) is a type of string
      port5_mode = lan.value["port5_mode"]
      # port5_ssid - (optional) is a type of string
      port5_ssid = lan.value["port5_ssid"]
      # port6_mode - (optional) is a type of string
      port6_mode = lan.value["port6_mode"]
      # port6_ssid - (optional) is a type of string
      port6_ssid = lan.value["port6_ssid"]
      # port7_mode - (optional) is a type of string
      port7_mode = lan.value["port7_mode"]
      # port7_ssid - (optional) is a type of string
      port7_ssid = lan.value["port7_ssid"]
      # port8_mode - (optional) is a type of string
      port8_mode = lan.value["port8_mode"]
      # port8_ssid - (optional) is a type of string
      port8_ssid = lan.value["port8_ssid"]
      # port_esl_mode - (optional) is a type of string
      port_esl_mode = lan.value["port_esl_mode"]
      # port_esl_ssid - (optional) is a type of string
      port_esl_ssid = lan.value["port_esl_ssid"]
      # port_mode - (optional) is a type of string
      port_mode = lan.value["port_mode"]
      # port_ssid - (optional) is a type of string
      port_ssid = lan.value["port_ssid"]
    }
  }

  dynamic "lbs" {
    for_each = var.lbs
    content {
      # aeroscout - (optional) is a type of string
      aeroscout = lbs.value["aeroscout"]
      # aeroscout_ap_mac - (optional) is a type of string
      aeroscout_ap_mac = lbs.value["aeroscout_ap_mac"]
      # aeroscout_mmu_report - (optional) is a type of string
      aeroscout_mmu_report = lbs.value["aeroscout_mmu_report"]
      # aeroscout_mu - (optional) is a type of string
      aeroscout_mu = lbs.value["aeroscout_mu"]
      # aeroscout_mu_factor - (optional) is a type of number
      aeroscout_mu_factor = lbs.value["aeroscout_mu_factor"]
      # aeroscout_mu_timeout - (optional) is a type of number
      aeroscout_mu_timeout = lbs.value["aeroscout_mu_timeout"]
      # aeroscout_server_ip - (optional) is a type of string
      aeroscout_server_ip = lbs.value["aeroscout_server_ip"]
      # aeroscout_server_port - (optional) is a type of number
      aeroscout_server_port = lbs.value["aeroscout_server_port"]
      # ekahau_blink_mode - (optional) is a type of string
      ekahau_blink_mode = lbs.value["ekahau_blink_mode"]
      # ekahau_tag - (optional) is a type of string
      ekahau_tag = lbs.value["ekahau_tag"]
      # erc_server_ip - (optional) is a type of string
      erc_server_ip = lbs.value["erc_server_ip"]
      # erc_server_port - (optional) is a type of number
      erc_server_port = lbs.value["erc_server_port"]
      # fortipresence - (optional) is a type of string
      fortipresence = lbs.value["fortipresence"]
      # fortipresence_ble - (optional) is a type of string
      fortipresence_ble = lbs.value["fortipresence_ble"]
      # fortipresence_frequency - (optional) is a type of number
      fortipresence_frequency = lbs.value["fortipresence_frequency"]
      # fortipresence_port - (optional) is a type of number
      fortipresence_port = lbs.value["fortipresence_port"]
      # fortipresence_project - (optional) is a type of string
      fortipresence_project = lbs.value["fortipresence_project"]
      # fortipresence_rogue - (optional) is a type of string
      fortipresence_rogue = lbs.value["fortipresence_rogue"]
      # fortipresence_secret - (optional) is a type of string
      fortipresence_secret = lbs.value["fortipresence_secret"]
      # fortipresence_server - (optional) is a type of string
      fortipresence_server = lbs.value["fortipresence_server"]
      # fortipresence_unassoc - (optional) is a type of string
      fortipresence_unassoc = lbs.value["fortipresence_unassoc"]
      # station_locate - (optional) is a type of string
      station_locate = lbs.value["station_locate"]
    }
  }

  dynamic "led_schedules" {
    for_each = var.led_schedules
    content {
      # name - (optional) is a type of string
      name = led_schedules.value["name"]
    }
  }

  dynamic "platform" {
    for_each = var.platform
    content {
      # ddscan - (optional) is a type of string
      ddscan = platform.value["ddscan"]
      # mode - (optional) is a type of string
      mode = platform.value["mode"]
      # type - (optional) is a type of string
      type = platform.value["type"]
    }
  }

  dynamic "radio_1" {
    for_each = var.radio_1
    content {
      # airtime_fairness - (optional) is a type of string
      airtime_fairness = radio_1.value["airtime_fairness"]
      # amsdu - (optional) is a type of string
      amsdu = radio_1.value["amsdu"]
      # ap_handoff - (optional) is a type of string
      ap_handoff = radio_1.value["ap_handoff"]
      # ap_sniffer_addr - (optional) is a type of string
      ap_sniffer_addr = radio_1.value["ap_sniffer_addr"]
      # ap_sniffer_bufsize - (optional) is a type of number
      ap_sniffer_bufsize = radio_1.value["ap_sniffer_bufsize"]
      # ap_sniffer_chan - (optional) is a type of number
      ap_sniffer_chan = radio_1.value["ap_sniffer_chan"]
      # ap_sniffer_ctl - (optional) is a type of string
      ap_sniffer_ctl = radio_1.value["ap_sniffer_ctl"]
      # ap_sniffer_data - (optional) is a type of string
      ap_sniffer_data = radio_1.value["ap_sniffer_data"]
      # ap_sniffer_mgmt_beacon - (optional) is a type of string
      ap_sniffer_mgmt_beacon = radio_1.value["ap_sniffer_mgmt_beacon"]
      # ap_sniffer_mgmt_other - (optional) is a type of string
      ap_sniffer_mgmt_other = radio_1.value["ap_sniffer_mgmt_other"]
      # ap_sniffer_mgmt_probe - (optional) is a type of string
      ap_sniffer_mgmt_probe = radio_1.value["ap_sniffer_mgmt_probe"]
      # auto_power_high - (optional) is a type of number
      auto_power_high = radio_1.value["auto_power_high"]
      # auto_power_level - (optional) is a type of string
      auto_power_level = radio_1.value["auto_power_level"]
      # auto_power_low - (optional) is a type of number
      auto_power_low = radio_1.value["auto_power_low"]
      # auto_power_target - (optional) is a type of string
      auto_power_target = radio_1.value["auto_power_target"]
      # band - (optional) is a type of string
      band = radio_1.value["band"]
      # band_5g_type - (optional) is a type of string
      band_5g_type = radio_1.value["band_5g_type"]
      # bandwidth_admission_control - (optional) is a type of string
      bandwidth_admission_control = radio_1.value["bandwidth_admission_control"]
      # bandwidth_capacity - (optional) is a type of number
      bandwidth_capacity = radio_1.value["bandwidth_capacity"]
      # beacon_interval - (optional) is a type of number
      beacon_interval = radio_1.value["beacon_interval"]
      # bss_color - (optional) is a type of number
      bss_color = radio_1.value["bss_color"]
      # call_admission_control - (optional) is a type of string
      call_admission_control = radio_1.value["call_admission_control"]
      # call_capacity - (optional) is a type of number
      call_capacity = radio_1.value["call_capacity"]
      # channel_bonding - (optional) is a type of string
      channel_bonding = radio_1.value["channel_bonding"]
      # channel_utilization - (optional) is a type of string
      channel_utilization = radio_1.value["channel_utilization"]
      # coexistence - (optional) is a type of string
      coexistence = radio_1.value["coexistence"]
      # darrp - (optional) is a type of string
      darrp = radio_1.value["darrp"]
      # drma - (optional) is a type of string
      drma = radio_1.value["drma"]
      # drma_sensitivity - (optional) is a type of string
      drma_sensitivity = radio_1.value["drma_sensitivity"]
      # dtim - (optional) is a type of number
      dtim = radio_1.value["dtim"]
      # frag_threshold - (optional) is a type of number
      frag_threshold = radio_1.value["frag_threshold"]
      # frequency_handoff - (optional) is a type of string
      frequency_handoff = radio_1.value["frequency_handoff"]
      # max_clients - (optional) is a type of number
      max_clients = radio_1.value["max_clients"]
      # max_distance - (optional) is a type of number
      max_distance = radio_1.value["max_distance"]
      # mode - (optional) is a type of string
      mode = radio_1.value["mode"]
      # power_level - (optional) is a type of number
      power_level = radio_1.value["power_level"]
      # powersave_optimize - (optional) is a type of string
      powersave_optimize = radio_1.value["powersave_optimize"]
      # protection_mode - (optional) is a type of string
      protection_mode = radio_1.value["protection_mode"]
      # radio_id - (optional) is a type of number
      radio_id = radio_1.value["radio_id"]
      # rts_threshold - (optional) is a type of number
      rts_threshold = radio_1.value["rts_threshold"]
      # short_guard_interval - (optional) is a type of string
      short_guard_interval = radio_1.value["short_guard_interval"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_1.value["spectrum_analysis"]
      # transmit_optimize - (optional) is a type of string
      transmit_optimize = radio_1.value["transmit_optimize"]
      # vap_all - (optional) is a type of string
      vap_all = radio_1.value["vap_all"]
      # wids_profile - (optional) is a type of string
      wids_profile = radio_1.value["wids_profile"]
      # zero_wait_dfs - (optional) is a type of string
      zero_wait_dfs = radio_1.value["zero_wait_dfs"]

      dynamic "channel" {
        for_each = radio_1.value.channel
        content {
          # chan - (optional) is a type of string
          chan = channel.value["chan"]
        }
      }

      dynamic "vaps" {
        for_each = radio_1.value.vaps
        content {
          # name - (optional) is a type of string
          name = vaps.value["name"]
        }
      }

    }
  }

  dynamic "radio_2" {
    for_each = var.radio_2
    content {
      # airtime_fairness - (optional) is a type of string
      airtime_fairness = radio_2.value["airtime_fairness"]
      # amsdu - (optional) is a type of string
      amsdu = radio_2.value["amsdu"]
      # ap_handoff - (optional) is a type of string
      ap_handoff = radio_2.value["ap_handoff"]
      # ap_sniffer_addr - (optional) is a type of string
      ap_sniffer_addr = radio_2.value["ap_sniffer_addr"]
      # ap_sniffer_bufsize - (optional) is a type of number
      ap_sniffer_bufsize = radio_2.value["ap_sniffer_bufsize"]
      # ap_sniffer_chan - (optional) is a type of number
      ap_sniffer_chan = radio_2.value["ap_sniffer_chan"]
      # ap_sniffer_ctl - (optional) is a type of string
      ap_sniffer_ctl = radio_2.value["ap_sniffer_ctl"]
      # ap_sniffer_data - (optional) is a type of string
      ap_sniffer_data = radio_2.value["ap_sniffer_data"]
      # ap_sniffer_mgmt_beacon - (optional) is a type of string
      ap_sniffer_mgmt_beacon = radio_2.value["ap_sniffer_mgmt_beacon"]
      # ap_sniffer_mgmt_other - (optional) is a type of string
      ap_sniffer_mgmt_other = radio_2.value["ap_sniffer_mgmt_other"]
      # ap_sniffer_mgmt_probe - (optional) is a type of string
      ap_sniffer_mgmt_probe = radio_2.value["ap_sniffer_mgmt_probe"]
      # auto_power_high - (optional) is a type of number
      auto_power_high = radio_2.value["auto_power_high"]
      # auto_power_level - (optional) is a type of string
      auto_power_level = radio_2.value["auto_power_level"]
      # auto_power_low - (optional) is a type of number
      auto_power_low = radio_2.value["auto_power_low"]
      # auto_power_target - (optional) is a type of string
      auto_power_target = radio_2.value["auto_power_target"]
      # band - (optional) is a type of string
      band = radio_2.value["band"]
      # band_5g_type - (optional) is a type of string
      band_5g_type = radio_2.value["band_5g_type"]
      # bandwidth_admission_control - (optional) is a type of string
      bandwidth_admission_control = radio_2.value["bandwidth_admission_control"]
      # bandwidth_capacity - (optional) is a type of number
      bandwidth_capacity = radio_2.value["bandwidth_capacity"]
      # beacon_interval - (optional) is a type of number
      beacon_interval = radio_2.value["beacon_interval"]
      # bss_color - (optional) is a type of number
      bss_color = radio_2.value["bss_color"]
      # call_admission_control - (optional) is a type of string
      call_admission_control = radio_2.value["call_admission_control"]
      # call_capacity - (optional) is a type of number
      call_capacity = radio_2.value["call_capacity"]
      # channel_bonding - (optional) is a type of string
      channel_bonding = radio_2.value["channel_bonding"]
      # channel_utilization - (optional) is a type of string
      channel_utilization = radio_2.value["channel_utilization"]
      # coexistence - (optional) is a type of string
      coexistence = radio_2.value["coexistence"]
      # darrp - (optional) is a type of string
      darrp = radio_2.value["darrp"]
      # drma - (optional) is a type of string
      drma = radio_2.value["drma"]
      # drma_sensitivity - (optional) is a type of string
      drma_sensitivity = radio_2.value["drma_sensitivity"]
      # dtim - (optional) is a type of number
      dtim = radio_2.value["dtim"]
      # frag_threshold - (optional) is a type of number
      frag_threshold = radio_2.value["frag_threshold"]
      # frequency_handoff - (optional) is a type of string
      frequency_handoff = radio_2.value["frequency_handoff"]
      # max_clients - (optional) is a type of number
      max_clients = radio_2.value["max_clients"]
      # max_distance - (optional) is a type of number
      max_distance = radio_2.value["max_distance"]
      # mode - (optional) is a type of string
      mode = radio_2.value["mode"]
      # power_level - (optional) is a type of number
      power_level = radio_2.value["power_level"]
      # powersave_optimize - (optional) is a type of string
      powersave_optimize = radio_2.value["powersave_optimize"]
      # protection_mode - (optional) is a type of string
      protection_mode = radio_2.value["protection_mode"]
      # radio_id - (optional) is a type of number
      radio_id = radio_2.value["radio_id"]
      # rts_threshold - (optional) is a type of number
      rts_threshold = radio_2.value["rts_threshold"]
      # short_guard_interval - (optional) is a type of string
      short_guard_interval = radio_2.value["short_guard_interval"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_2.value["spectrum_analysis"]
      # transmit_optimize - (optional) is a type of string
      transmit_optimize = radio_2.value["transmit_optimize"]
      # vap_all - (optional) is a type of string
      vap_all = radio_2.value["vap_all"]
      # wids_profile - (optional) is a type of string
      wids_profile = radio_2.value["wids_profile"]
      # zero_wait_dfs - (optional) is a type of string
      zero_wait_dfs = radio_2.value["zero_wait_dfs"]

      dynamic "channel" {
        for_each = radio_2.value.channel
        content {
          # chan - (optional) is a type of string
          chan = channel.value["chan"]
        }
      }

      dynamic "vaps" {
        for_each = radio_2.value.vaps
        content {
          # name - (optional) is a type of string
          name = vaps.value["name"]
        }
      }

    }
  }

  dynamic "radio_3" {
    for_each = var.radio_3
    content {
      # airtime_fairness - (optional) is a type of string
      airtime_fairness = radio_3.value["airtime_fairness"]
      # amsdu - (optional) is a type of string
      amsdu = radio_3.value["amsdu"]
      # ap_handoff - (optional) is a type of string
      ap_handoff = radio_3.value["ap_handoff"]
      # ap_sniffer_addr - (optional) is a type of string
      ap_sniffer_addr = radio_3.value["ap_sniffer_addr"]
      # ap_sniffer_bufsize - (optional) is a type of number
      ap_sniffer_bufsize = radio_3.value["ap_sniffer_bufsize"]
      # ap_sniffer_chan - (optional) is a type of number
      ap_sniffer_chan = radio_3.value["ap_sniffer_chan"]
      # ap_sniffer_ctl - (optional) is a type of string
      ap_sniffer_ctl = radio_3.value["ap_sniffer_ctl"]
      # ap_sniffer_data - (optional) is a type of string
      ap_sniffer_data = radio_3.value["ap_sniffer_data"]
      # ap_sniffer_mgmt_beacon - (optional) is a type of string
      ap_sniffer_mgmt_beacon = radio_3.value["ap_sniffer_mgmt_beacon"]
      # ap_sniffer_mgmt_other - (optional) is a type of string
      ap_sniffer_mgmt_other = radio_3.value["ap_sniffer_mgmt_other"]
      # ap_sniffer_mgmt_probe - (optional) is a type of string
      ap_sniffer_mgmt_probe = radio_3.value["ap_sniffer_mgmt_probe"]
      # auto_power_high - (optional) is a type of number
      auto_power_high = radio_3.value["auto_power_high"]
      # auto_power_level - (optional) is a type of string
      auto_power_level = radio_3.value["auto_power_level"]
      # auto_power_low - (optional) is a type of number
      auto_power_low = radio_3.value["auto_power_low"]
      # auto_power_target - (optional) is a type of string
      auto_power_target = radio_3.value["auto_power_target"]
      # band - (optional) is a type of string
      band = radio_3.value["band"]
      # band_5g_type - (optional) is a type of string
      band_5g_type = radio_3.value["band_5g_type"]
      # bandwidth_admission_control - (optional) is a type of string
      bandwidth_admission_control = radio_3.value["bandwidth_admission_control"]
      # bandwidth_capacity - (optional) is a type of number
      bandwidth_capacity = radio_3.value["bandwidth_capacity"]
      # beacon_interval - (optional) is a type of number
      beacon_interval = radio_3.value["beacon_interval"]
      # bss_color - (optional) is a type of number
      bss_color = radio_3.value["bss_color"]
      # call_admission_control - (optional) is a type of string
      call_admission_control = radio_3.value["call_admission_control"]
      # call_capacity - (optional) is a type of number
      call_capacity = radio_3.value["call_capacity"]
      # channel_bonding - (optional) is a type of string
      channel_bonding = radio_3.value["channel_bonding"]
      # channel_utilization - (optional) is a type of string
      channel_utilization = radio_3.value["channel_utilization"]
      # coexistence - (optional) is a type of string
      coexistence = radio_3.value["coexistence"]
      # darrp - (optional) is a type of string
      darrp = radio_3.value["darrp"]
      # drma - (optional) is a type of string
      drma = radio_3.value["drma"]
      # drma_sensitivity - (optional) is a type of string
      drma_sensitivity = radio_3.value["drma_sensitivity"]
      # dtim - (optional) is a type of number
      dtim = radio_3.value["dtim"]
      # frag_threshold - (optional) is a type of number
      frag_threshold = radio_3.value["frag_threshold"]
      # frequency_handoff - (optional) is a type of string
      frequency_handoff = radio_3.value["frequency_handoff"]
      # max_clients - (optional) is a type of number
      max_clients = radio_3.value["max_clients"]
      # max_distance - (optional) is a type of number
      max_distance = radio_3.value["max_distance"]
      # mode - (optional) is a type of string
      mode = radio_3.value["mode"]
      # power_level - (optional) is a type of number
      power_level = radio_3.value["power_level"]
      # powersave_optimize - (optional) is a type of string
      powersave_optimize = radio_3.value["powersave_optimize"]
      # protection_mode - (optional) is a type of string
      protection_mode = radio_3.value["protection_mode"]
      # rts_threshold - (optional) is a type of number
      rts_threshold = radio_3.value["rts_threshold"]
      # short_guard_interval - (optional) is a type of string
      short_guard_interval = radio_3.value["short_guard_interval"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_3.value["spectrum_analysis"]
      # transmit_optimize - (optional) is a type of string
      transmit_optimize = radio_3.value["transmit_optimize"]
      # vap_all - (optional) is a type of string
      vap_all = radio_3.value["vap_all"]
      # wids_profile - (optional) is a type of string
      wids_profile = radio_3.value["wids_profile"]
      # zero_wait_dfs - (optional) is a type of string
      zero_wait_dfs = radio_3.value["zero_wait_dfs"]

      dynamic "channel" {
        for_each = radio_3.value.channel
        content {
          # chan - (optional) is a type of string
          chan = channel.value["chan"]
        }
      }

      dynamic "vaps" {
        for_each = radio_3.value.vaps
        content {
          # name - (optional) is a type of string
          name = vaps.value["name"]
        }
      }

    }
  }

  dynamic "radio_4" {
    for_each = var.radio_4
    content {
      # airtime_fairness - (optional) is a type of string
      airtime_fairness = radio_4.value["airtime_fairness"]
      # amsdu - (optional) is a type of string
      amsdu = radio_4.value["amsdu"]
      # ap_handoff - (optional) is a type of string
      ap_handoff = radio_4.value["ap_handoff"]
      # ap_sniffer_addr - (optional) is a type of string
      ap_sniffer_addr = radio_4.value["ap_sniffer_addr"]
      # ap_sniffer_bufsize - (optional) is a type of number
      ap_sniffer_bufsize = radio_4.value["ap_sniffer_bufsize"]
      # ap_sniffer_chan - (optional) is a type of number
      ap_sniffer_chan = radio_4.value["ap_sniffer_chan"]
      # ap_sniffer_ctl - (optional) is a type of string
      ap_sniffer_ctl = radio_4.value["ap_sniffer_ctl"]
      # ap_sniffer_data - (optional) is a type of string
      ap_sniffer_data = radio_4.value["ap_sniffer_data"]
      # ap_sniffer_mgmt_beacon - (optional) is a type of string
      ap_sniffer_mgmt_beacon = radio_4.value["ap_sniffer_mgmt_beacon"]
      # ap_sniffer_mgmt_other - (optional) is a type of string
      ap_sniffer_mgmt_other = radio_4.value["ap_sniffer_mgmt_other"]
      # ap_sniffer_mgmt_probe - (optional) is a type of string
      ap_sniffer_mgmt_probe = radio_4.value["ap_sniffer_mgmt_probe"]
      # auto_power_high - (optional) is a type of number
      auto_power_high = radio_4.value["auto_power_high"]
      # auto_power_level - (optional) is a type of string
      auto_power_level = radio_4.value["auto_power_level"]
      # auto_power_low - (optional) is a type of number
      auto_power_low = radio_4.value["auto_power_low"]
      # auto_power_target - (optional) is a type of string
      auto_power_target = radio_4.value["auto_power_target"]
      # band - (optional) is a type of string
      band = radio_4.value["band"]
      # band_5g_type - (optional) is a type of string
      band_5g_type = radio_4.value["band_5g_type"]
      # bandwidth_admission_control - (optional) is a type of string
      bandwidth_admission_control = radio_4.value["bandwidth_admission_control"]
      # bandwidth_capacity - (optional) is a type of number
      bandwidth_capacity = radio_4.value["bandwidth_capacity"]
      # beacon_interval - (optional) is a type of number
      beacon_interval = radio_4.value["beacon_interval"]
      # bss_color - (optional) is a type of number
      bss_color = radio_4.value["bss_color"]
      # call_admission_control - (optional) is a type of string
      call_admission_control = radio_4.value["call_admission_control"]
      # call_capacity - (optional) is a type of number
      call_capacity = radio_4.value["call_capacity"]
      # channel_bonding - (optional) is a type of string
      channel_bonding = radio_4.value["channel_bonding"]
      # channel_utilization - (optional) is a type of string
      channel_utilization = radio_4.value["channel_utilization"]
      # coexistence - (optional) is a type of string
      coexistence = radio_4.value["coexistence"]
      # darrp - (optional) is a type of string
      darrp = radio_4.value["darrp"]
      # drma - (optional) is a type of string
      drma = radio_4.value["drma"]
      # drma_sensitivity - (optional) is a type of string
      drma_sensitivity = radio_4.value["drma_sensitivity"]
      # dtim - (optional) is a type of number
      dtim = radio_4.value["dtim"]
      # frag_threshold - (optional) is a type of number
      frag_threshold = radio_4.value["frag_threshold"]
      # frequency_handoff - (optional) is a type of string
      frequency_handoff = radio_4.value["frequency_handoff"]
      # max_clients - (optional) is a type of number
      max_clients = radio_4.value["max_clients"]
      # max_distance - (optional) is a type of number
      max_distance = radio_4.value["max_distance"]
      # mode - (optional) is a type of string
      mode = radio_4.value["mode"]
      # power_level - (optional) is a type of number
      power_level = radio_4.value["power_level"]
      # powersave_optimize - (optional) is a type of string
      powersave_optimize = radio_4.value["powersave_optimize"]
      # protection_mode - (optional) is a type of string
      protection_mode = radio_4.value["protection_mode"]
      # rts_threshold - (optional) is a type of number
      rts_threshold = radio_4.value["rts_threshold"]
      # short_guard_interval - (optional) is a type of string
      short_guard_interval = radio_4.value["short_guard_interval"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_4.value["spectrum_analysis"]
      # transmit_optimize - (optional) is a type of string
      transmit_optimize = radio_4.value["transmit_optimize"]
      # vap_all - (optional) is a type of string
      vap_all = radio_4.value["vap_all"]
      # wids_profile - (optional) is a type of string
      wids_profile = radio_4.value["wids_profile"]
      # zero_wait_dfs - (optional) is a type of string
      zero_wait_dfs = radio_4.value["zero_wait_dfs"]

      dynamic "channel" {
        for_each = radio_4.value.channel
        content {
          # chan - (optional) is a type of string
          chan = channel.value["chan"]
        }
      }

      dynamic "vaps" {
        for_each = radio_4.value.vaps
        content {
          # name - (optional) is a type of string
          name = vaps.value["name"]
        }
      }

    }
  }

  dynamic "split_tunneling_acl" {
    for_each = var.split_tunneling_acl
    content {
      # dest_ip - (optional) is a type of string
      dest_ip = split_tunneling_acl.value["dest_ip"]
      # id - (optional) is a type of number
      id = split_tunneling_acl.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allowaccess" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.allowaccess
}

output "ap_country" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.ap_country
}

output "ap_handoff" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.ap_handoff
}

output "apcfg_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.apcfg_profile
}

output "ble_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.ble_profile
}

output "control_message_offload" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.control_message_offload
}

output "dtls_in_kernel" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.dtls_in_kernel
}

output "dtls_policy" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.dtls_policy
}

output "energy_efficient_ethernet" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.energy_efficient_ethernet
}

output "ext_info_enable" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.ext_info_enable
}

output "frequency_handoff" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.frequency_handoff
}

output "handoff_roaming" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.handoff_roaming
}

output "handoff_rssi" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtpprofile.this.handoff_rssi
}

output "handoff_sta_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtpprofile.this.handoff_sta_thresh
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.id
}

output "ip_fragment_preventing" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.ip_fragment_preventing
}

output "led_state" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.led_state
}

output "lldp" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.lldp
}

output "login_passwd_change" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.login_passwd_change
}

output "max_clients" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtpprofile.this.max_clients
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.name
}

output "poe_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.poe_mode
}

output "split_tunneling_acl_local_ap_subnet" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.split_tunneling_acl_local_ap_subnet
}

output "split_tunneling_acl_path" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.split_tunneling_acl_path
}

output "tun_mtu_downlink" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtpprofile.this.tun_mtu_downlink
}

output "tun_mtu_uplink" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtpprofile.this.tun_mtu_uplink
}

output "wan_port_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpprofile.this.wan_port_mode
}

output "this" {
  value = fortios_wirelesscontroller_wtpprofile.this
}
```

[top](#index)