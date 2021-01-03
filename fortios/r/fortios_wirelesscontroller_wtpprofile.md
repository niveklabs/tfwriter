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
    fortios = ">= 1.6.18"
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
  # energy_efficient_ethernet - (optional) is a type of string
  energy_efficient_ethernet = null
  # ext_info_enable - (optional) is a type of string
  ext_info_enable = null
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
    port1_mode = null
    port1_ssid = null
    port2_mode = null
    port2_ssid = null
    port3_mode = null
    port3_ssid = null
    port4_mode = null
    port4_ssid = null
    port5_mode = null
    port5_ssid = null
    port6_mode = null
    port6_ssid = null
    port7_mode = null
    port7_ssid = null
    port8_mode = null
    port8_ssid = null
    port_mode  = null
    port_ssid  = null
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
    type = null
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
    band                        = null
    bandwidth_admission_control = null
    bandwidth_capacity          = null
    beacon_interval             = null
    call_admission_control      = null
    call_capacity               = null
    channel = [{
      chan = null
    }]
    channel_bonding      = null
    channel_utilization  = null
    coexistence          = null
    darrp                = null
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
    wids_profile = null
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
    band                        = null
    bandwidth_admission_control = null
    bandwidth_capacity          = null
    beacon_interval             = null
    call_admission_control      = null
    call_capacity               = null
    channel = [{
      chan = null
    }]
    channel_bonding      = null
    channel_utilization  = null
    coexistence          = null
    darrp                = null
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
    wids_profile = null
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
      port1_mode = string
      port1_ssid = string
      port2_mode = string
      port2_ssid = string
      port3_mode = string
      port3_ssid = string
      port4_mode = string
      port4_ssid = string
      port5_mode = string
      port5_ssid = string
      port6_mode = string
      port6_ssid = string
      port7_mode = string
      port7_ssid = string
      port8_mode = string
      port8_ssid = string
      port_mode  = string
      port_ssid  = string
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
      type = string
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
      band                        = string
      bandwidth_admission_control = string
      bandwidth_capacity          = number
      beacon_interval             = number
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
      wids_profile = string
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
      band                        = string
      bandwidth_admission_control = string
      bandwidth_capacity          = number
      beacon_interval             = number
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
      wids_profile = string
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
  allowaccess                         = var.allowaccess
  ap_country                          = var.ap_country
  ble_profile                         = var.ble_profile
  comment                             = var.comment
  control_message_offload             = var.control_message_offload
  dtls_in_kernel                      = var.dtls_in_kernel
  dtls_policy                         = var.dtls_policy
  energy_efficient_ethernet           = var.energy_efficient_ethernet
  ext_info_enable                     = var.ext_info_enable
  handoff_roaming                     = var.handoff_roaming
  handoff_rssi                        = var.handoff_rssi
  handoff_sta_thresh                  = var.handoff_sta_thresh
  ip_fragment_preventing              = var.ip_fragment_preventing
  led_state                           = var.led_state
  lldp                                = var.lldp
  login_passwd                        = var.login_passwd
  login_passwd_change                 = var.login_passwd_change
  max_clients                         = var.max_clients
  name                                = var.name
  poe_mode                            = var.poe_mode
  split_tunneling_acl_local_ap_subnet = var.split_tunneling_acl_local_ap_subnet
  split_tunneling_acl_path            = var.split_tunneling_acl_path
  tun_mtu_downlink                    = var.tun_mtu_downlink
  tun_mtu_uplink                      = var.tun_mtu_uplink
  wan_port_mode                       = var.wan_port_mode

  dynamic "deny_mac_list" {
    for_each = var.deny_mac_list
    content {
      id  = deny_mac_list.value["id"]
      mac = deny_mac_list.value["mac"]
    }
  }

  dynamic "lan" {
    for_each = var.lan
    content {
      port1_mode = lan.value["port1_mode"]
      port1_ssid = lan.value["port1_ssid"]
      port2_mode = lan.value["port2_mode"]
      port2_ssid = lan.value["port2_ssid"]
      port3_mode = lan.value["port3_mode"]
      port3_ssid = lan.value["port3_ssid"]
      port4_mode = lan.value["port4_mode"]
      port4_ssid = lan.value["port4_ssid"]
      port5_mode = lan.value["port5_mode"]
      port5_ssid = lan.value["port5_ssid"]
      port6_mode = lan.value["port6_mode"]
      port6_ssid = lan.value["port6_ssid"]
      port7_mode = lan.value["port7_mode"]
      port7_ssid = lan.value["port7_ssid"]
      port8_mode = lan.value["port8_mode"]
      port8_ssid = lan.value["port8_ssid"]
      port_mode  = lan.value["port_mode"]
      port_ssid  = lan.value["port_ssid"]
    }
  }

  dynamic "lbs" {
    for_each = var.lbs
    content {
      aeroscout               = lbs.value["aeroscout"]
      aeroscout_ap_mac        = lbs.value["aeroscout_ap_mac"]
      aeroscout_mmu_report    = lbs.value["aeroscout_mmu_report"]
      aeroscout_mu            = lbs.value["aeroscout_mu"]
      aeroscout_mu_factor     = lbs.value["aeroscout_mu_factor"]
      aeroscout_mu_timeout    = lbs.value["aeroscout_mu_timeout"]
      aeroscout_server_ip     = lbs.value["aeroscout_server_ip"]
      aeroscout_server_port   = lbs.value["aeroscout_server_port"]
      ekahau_blink_mode       = lbs.value["ekahau_blink_mode"]
      ekahau_tag              = lbs.value["ekahau_tag"]
      erc_server_ip           = lbs.value["erc_server_ip"]
      erc_server_port         = lbs.value["erc_server_port"]
      fortipresence           = lbs.value["fortipresence"]
      fortipresence_frequency = lbs.value["fortipresence_frequency"]
      fortipresence_port      = lbs.value["fortipresence_port"]
      fortipresence_project   = lbs.value["fortipresence_project"]
      fortipresence_rogue     = lbs.value["fortipresence_rogue"]
      fortipresence_secret    = lbs.value["fortipresence_secret"]
      fortipresence_server    = lbs.value["fortipresence_server"]
      fortipresence_unassoc   = lbs.value["fortipresence_unassoc"]
      station_locate          = lbs.value["station_locate"]
    }
  }

  dynamic "led_schedules" {
    for_each = var.led_schedules
    content {
      name = led_schedules.value["name"]
    }
  }

  dynamic "platform" {
    for_each = var.platform
    content {
      type = platform.value["type"]
    }
  }

  dynamic "radio_1" {
    for_each = var.radio_1
    content {
      airtime_fairness            = radio_1.value["airtime_fairness"]
      amsdu                       = radio_1.value["amsdu"]
      ap_handoff                  = radio_1.value["ap_handoff"]
      ap_sniffer_addr             = radio_1.value["ap_sniffer_addr"]
      ap_sniffer_bufsize          = radio_1.value["ap_sniffer_bufsize"]
      ap_sniffer_chan             = radio_1.value["ap_sniffer_chan"]
      ap_sniffer_ctl              = radio_1.value["ap_sniffer_ctl"]
      ap_sniffer_data             = radio_1.value["ap_sniffer_data"]
      ap_sniffer_mgmt_beacon      = radio_1.value["ap_sniffer_mgmt_beacon"]
      ap_sniffer_mgmt_other       = radio_1.value["ap_sniffer_mgmt_other"]
      ap_sniffer_mgmt_probe       = radio_1.value["ap_sniffer_mgmt_probe"]
      auto_power_high             = radio_1.value["auto_power_high"]
      auto_power_level            = radio_1.value["auto_power_level"]
      auto_power_low              = radio_1.value["auto_power_low"]
      band                        = radio_1.value["band"]
      bandwidth_admission_control = radio_1.value["bandwidth_admission_control"]
      bandwidth_capacity          = radio_1.value["bandwidth_capacity"]
      beacon_interval             = radio_1.value["beacon_interval"]
      call_admission_control      = radio_1.value["call_admission_control"]
      call_capacity               = radio_1.value["call_capacity"]
      channel_bonding             = radio_1.value["channel_bonding"]
      channel_utilization         = radio_1.value["channel_utilization"]
      coexistence                 = radio_1.value["coexistence"]
      darrp                       = radio_1.value["darrp"]
      dtim                        = radio_1.value["dtim"]
      frag_threshold              = radio_1.value["frag_threshold"]
      frequency_handoff           = radio_1.value["frequency_handoff"]
      max_clients                 = radio_1.value["max_clients"]
      max_distance                = radio_1.value["max_distance"]
      mode                        = radio_1.value["mode"]
      power_level                 = radio_1.value["power_level"]
      powersave_optimize          = radio_1.value["powersave_optimize"]
      protection_mode             = radio_1.value["protection_mode"]
      radio_id                    = radio_1.value["radio_id"]
      rts_threshold               = radio_1.value["rts_threshold"]
      short_guard_interval        = radio_1.value["short_guard_interval"]
      spectrum_analysis           = radio_1.value["spectrum_analysis"]
      transmit_optimize           = radio_1.value["transmit_optimize"]
      vap_all                     = radio_1.value["vap_all"]
      wids_profile                = radio_1.value["wids_profile"]

      dynamic "channel" {
        for_each = radio_1.value.channel
        content {
          chan = channel.value["chan"]
        }
      }

      dynamic "vaps" {
        for_each = radio_1.value.vaps
        content {
          name = vaps.value["name"]
        }
      }

    }
  }

  dynamic "radio_2" {
    for_each = var.radio_2
    content {
      airtime_fairness            = radio_2.value["airtime_fairness"]
      amsdu                       = radio_2.value["amsdu"]
      ap_handoff                  = radio_2.value["ap_handoff"]
      ap_sniffer_addr             = radio_2.value["ap_sniffer_addr"]
      ap_sniffer_bufsize          = radio_2.value["ap_sniffer_bufsize"]
      ap_sniffer_chan             = radio_2.value["ap_sniffer_chan"]
      ap_sniffer_ctl              = radio_2.value["ap_sniffer_ctl"]
      ap_sniffer_data             = radio_2.value["ap_sniffer_data"]
      ap_sniffer_mgmt_beacon      = radio_2.value["ap_sniffer_mgmt_beacon"]
      ap_sniffer_mgmt_other       = radio_2.value["ap_sniffer_mgmt_other"]
      ap_sniffer_mgmt_probe       = radio_2.value["ap_sniffer_mgmt_probe"]
      auto_power_high             = radio_2.value["auto_power_high"]
      auto_power_level            = radio_2.value["auto_power_level"]
      auto_power_low              = radio_2.value["auto_power_low"]
      band                        = radio_2.value["band"]
      bandwidth_admission_control = radio_2.value["bandwidth_admission_control"]
      bandwidth_capacity          = radio_2.value["bandwidth_capacity"]
      beacon_interval             = radio_2.value["beacon_interval"]
      call_admission_control      = radio_2.value["call_admission_control"]
      call_capacity               = radio_2.value["call_capacity"]
      channel_bonding             = radio_2.value["channel_bonding"]
      channel_utilization         = radio_2.value["channel_utilization"]
      coexistence                 = radio_2.value["coexistence"]
      darrp                       = radio_2.value["darrp"]
      dtim                        = radio_2.value["dtim"]
      frag_threshold              = radio_2.value["frag_threshold"]
      frequency_handoff           = radio_2.value["frequency_handoff"]
      max_clients                 = radio_2.value["max_clients"]
      max_distance                = radio_2.value["max_distance"]
      mode                        = radio_2.value["mode"]
      power_level                 = radio_2.value["power_level"]
      powersave_optimize          = radio_2.value["powersave_optimize"]
      protection_mode             = radio_2.value["protection_mode"]
      radio_id                    = radio_2.value["radio_id"]
      rts_threshold               = radio_2.value["rts_threshold"]
      short_guard_interval        = radio_2.value["short_guard_interval"]
      spectrum_analysis           = radio_2.value["spectrum_analysis"]
      transmit_optimize           = radio_2.value["transmit_optimize"]
      vap_all                     = radio_2.value["vap_all"]
      wids_profile                = radio_2.value["wids_profile"]

      dynamic "channel" {
        for_each = radio_2.value.channel
        content {
          chan = channel.value["chan"]
        }
      }

      dynamic "vaps" {
        for_each = radio_2.value.vaps
        content {
          name = vaps.value["name"]
        }
      }

    }
  }

  dynamic "split_tunneling_acl" {
    for_each = var.split_tunneling_acl
    content {
      dest_ip = split_tunneling_acl.value["dest_ip"]
      id      = split_tunneling_acl.value["id"]
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