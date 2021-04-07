# fortios_wirelesscontroller_wtp

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
module "fortios_wirelesscontroller_wtp" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_wtp"

  # admin - (optional) is a type of string
  admin = null
  # allowaccess - (optional) is a type of string
  allowaccess = null
  # apcfg_profile - (optional) is a type of string
  apcfg_profile = null
  # bonjour_profile - (optional) is a type of string
  bonjour_profile = null
  # coordinate_latitude - (optional) is a type of string
  coordinate_latitude = null
  # coordinate_longitude - (optional) is a type of string
  coordinate_longitude = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # firmware_provision - (optional) is a type of string
  firmware_provision = null
  # image_download - (optional) is a type of string
  image_download = null
  # index - (optional) is a type of number
  index = null
  # ip_fragment_preventing - (optional) is a type of string
  ip_fragment_preventing = null
  # led_state - (optional) is a type of string
  led_state = null
  # location - (optional) is a type of string
  location = null
  # login_passwd - (optional) is a type of string
  login_passwd = null
  # login_passwd_change - (optional) is a type of string
  login_passwd_change = null
  # mesh_bridge_enable - (optional) is a type of string
  mesh_bridge_enable = null
  # name - (optional) is a type of string
  name = null
  # override_allowaccess - (optional) is a type of string
  override_allowaccess = null
  # override_ip_fragment - (optional) is a type of string
  override_ip_fragment = null
  # override_lan - (optional) is a type of string
  override_lan = null
  # override_led_state - (optional) is a type of string
  override_led_state = null
  # override_login_passwd_change - (optional) is a type of string
  override_login_passwd_change = null
  # override_split_tunnel - (optional) is a type of string
  override_split_tunnel = null
  # override_wan_port_mode - (optional) is a type of string
  override_wan_port_mode = null
  # region - (optional) is a type of string
  region = null
  # region_x - (optional) is a type of string
  region_x = null
  # region_y - (optional) is a type of string
  region_y = null
  # split_tunneling_acl_local_ap_subnet - (optional) is a type of string
  split_tunneling_acl_local_ap_subnet = null
  # split_tunneling_acl_path - (optional) is a type of string
  split_tunneling_acl_path = null
  # tun_mtu_downlink - (optional) is a type of number
  tun_mtu_downlink = null
  # tun_mtu_uplink - (optional) is a type of number
  tun_mtu_uplink = null
  # uuid - (optional) is a type of string
  uuid = null
  # wan_port_mode - (optional) is a type of string
  wan_port_mode = null
  # wtp_id - (optional) is a type of string
  wtp_id = null
  # wtp_mode - (optional) is a type of string
  wtp_mode = null
  # wtp_profile - (required) is a type of string
  wtp_profile = null

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

  radio_1 = [{
    auto_power_high   = null
    auto_power_level  = null
    auto_power_low    = null
    auto_power_target = null
    band              = null
    channel = [{
      chan = null
    }]
    drma_manual_mode  = null
    override_analysis = null
    override_band     = null
    override_channel  = null
    override_txpower  = null
    override_vaps     = null
    power_level       = null
    radio_id          = null
    spectrum_analysis = null
    vap_all           = null
    vaps = [{
      name = null
    }]
  }]

  radio_2 = [{
    auto_power_high   = null
    auto_power_level  = null
    auto_power_low    = null
    auto_power_target = null
    band              = null
    channel = [{
      chan = null
    }]
    drma_manual_mode  = null
    override_analysis = null
    override_band     = null
    override_channel  = null
    override_txpower  = null
    override_vaps     = null
    power_level       = null
    radio_id          = null
    spectrum_analysis = null
    vap_all           = null
    vaps = [{
      name = null
    }]
  }]

  radio_3 = [{
    auto_power_high   = null
    auto_power_level  = null
    auto_power_low    = null
    auto_power_target = null
    band              = null
    channel = [{
      chan = null
    }]
    drma_manual_mode  = null
    override_analysis = null
    override_band     = null
    override_channel  = null
    override_txpower  = null
    override_vaps     = null
    power_level       = null
    spectrum_analysis = null
    vap_all           = null
    vaps = [{
      name = null
    }]
  }]

  radio_4 = [{
    auto_power_high   = null
    auto_power_level  = null
    auto_power_low    = null
    auto_power_target = null
    band              = null
    channel = [{
      chan = null
    }]
    drma_manual_mode  = null
    override_analysis = null
    override_band     = null
    override_channel  = null
    override_txpower  = null
    override_vaps     = null
    power_level       = null
    spectrum_analysis = null
    vap_all           = null
    vaps = [{
      name = null
    }]
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
variable "admin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "apcfg_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bonjour_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "coordinate_latitude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "coordinate_longitude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firmware_provision" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_download" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "index" {
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

variable "location" {
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

variable "mesh_bridge_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_ip_fragment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_lan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_led_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_login_passwd_change" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_split_tunnel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_wan_port_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_x" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_y" {
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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wan_port_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wtp_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wtp_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wtp_profile" {
  description = "(required)"
  type        = string
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

variable "radio_1" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_power_high   = number
      auto_power_level  = string
      auto_power_low    = number
      auto_power_target = string
      band              = string
      channel = list(object(
        {
          chan = string
        }
      ))
      drma_manual_mode  = string
      override_analysis = string
      override_band     = string
      override_channel  = string
      override_txpower  = string
      override_vaps     = string
      power_level       = number
      radio_id          = number
      spectrum_analysis = string
      vap_all           = string
      vaps = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "radio_2" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_power_high   = number
      auto_power_level  = string
      auto_power_low    = number
      auto_power_target = string
      band              = string
      channel = list(object(
        {
          chan = string
        }
      ))
      drma_manual_mode  = string
      override_analysis = string
      override_band     = string
      override_channel  = string
      override_txpower  = string
      override_vaps     = string
      power_level       = number
      radio_id          = number
      spectrum_analysis = string
      vap_all           = string
      vaps = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "radio_3" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_power_high   = number
      auto_power_level  = string
      auto_power_low    = number
      auto_power_target = string
      band              = string
      channel = list(object(
        {
          chan = string
        }
      ))
      drma_manual_mode  = string
      override_analysis = string
      override_band     = string
      override_channel  = string
      override_txpower  = string
      override_vaps     = string
      power_level       = number
      spectrum_analysis = string
      vap_all           = string
      vaps = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "radio_4" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_power_high   = number
      auto_power_level  = string
      auto_power_low    = number
      auto_power_target = string
      band              = string
      channel = list(object(
        {
          chan = string
        }
      ))
      drma_manual_mode  = string
      override_analysis = string
      override_band     = string
      override_channel  = string
      override_txpower  = string
      override_vaps     = string
      power_level       = number
      spectrum_analysis = string
      vap_all           = string
      vaps = list(object(
        {
          name = string
        }
      ))
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
resource "fortios_wirelesscontroller_wtp" "this" {
  # admin - (optional) is a type of string
  admin = var.admin
  # allowaccess - (optional) is a type of string
  allowaccess = var.allowaccess
  # apcfg_profile - (optional) is a type of string
  apcfg_profile = var.apcfg_profile
  # bonjour_profile - (optional) is a type of string
  bonjour_profile = var.bonjour_profile
  # coordinate_latitude - (optional) is a type of string
  coordinate_latitude = var.coordinate_latitude
  # coordinate_longitude - (optional) is a type of string
  coordinate_longitude = var.coordinate_longitude
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # firmware_provision - (optional) is a type of string
  firmware_provision = var.firmware_provision
  # image_download - (optional) is a type of string
  image_download = var.image_download
  # index - (optional) is a type of number
  index = var.index
  # ip_fragment_preventing - (optional) is a type of string
  ip_fragment_preventing = var.ip_fragment_preventing
  # led_state - (optional) is a type of string
  led_state = var.led_state
  # location - (optional) is a type of string
  location = var.location
  # login_passwd - (optional) is a type of string
  login_passwd = var.login_passwd
  # login_passwd_change - (optional) is a type of string
  login_passwd_change = var.login_passwd_change
  # mesh_bridge_enable - (optional) is a type of string
  mesh_bridge_enable = var.mesh_bridge_enable
  # name - (optional) is a type of string
  name = var.name
  # override_allowaccess - (optional) is a type of string
  override_allowaccess = var.override_allowaccess
  # override_ip_fragment - (optional) is a type of string
  override_ip_fragment = var.override_ip_fragment
  # override_lan - (optional) is a type of string
  override_lan = var.override_lan
  # override_led_state - (optional) is a type of string
  override_led_state = var.override_led_state
  # override_login_passwd_change - (optional) is a type of string
  override_login_passwd_change = var.override_login_passwd_change
  # override_split_tunnel - (optional) is a type of string
  override_split_tunnel = var.override_split_tunnel
  # override_wan_port_mode - (optional) is a type of string
  override_wan_port_mode = var.override_wan_port_mode
  # region - (optional) is a type of string
  region = var.region
  # region_x - (optional) is a type of string
  region_x = var.region_x
  # region_y - (optional) is a type of string
  region_y = var.region_y
  # split_tunneling_acl_local_ap_subnet - (optional) is a type of string
  split_tunneling_acl_local_ap_subnet = var.split_tunneling_acl_local_ap_subnet
  # split_tunneling_acl_path - (optional) is a type of string
  split_tunneling_acl_path = var.split_tunneling_acl_path
  # tun_mtu_downlink - (optional) is a type of number
  tun_mtu_downlink = var.tun_mtu_downlink
  # tun_mtu_uplink - (optional) is a type of number
  tun_mtu_uplink = var.tun_mtu_uplink
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # wan_port_mode - (optional) is a type of string
  wan_port_mode = var.wan_port_mode
  # wtp_id - (optional) is a type of string
  wtp_id = var.wtp_id
  # wtp_mode - (optional) is a type of string
  wtp_mode = var.wtp_mode
  # wtp_profile - (required) is a type of string
  wtp_profile = var.wtp_profile

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

  dynamic "radio_1" {
    for_each = var.radio_1
    content {
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
      # drma_manual_mode - (optional) is a type of string
      drma_manual_mode = radio_1.value["drma_manual_mode"]
      # override_analysis - (optional) is a type of string
      override_analysis = radio_1.value["override_analysis"]
      # override_band - (optional) is a type of string
      override_band = radio_1.value["override_band"]
      # override_channel - (optional) is a type of string
      override_channel = radio_1.value["override_channel"]
      # override_txpower - (optional) is a type of string
      override_txpower = radio_1.value["override_txpower"]
      # override_vaps - (optional) is a type of string
      override_vaps = radio_1.value["override_vaps"]
      # power_level - (optional) is a type of number
      power_level = radio_1.value["power_level"]
      # radio_id - (optional) is a type of number
      radio_id = radio_1.value["radio_id"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_1.value["spectrum_analysis"]
      # vap_all - (optional) is a type of string
      vap_all = radio_1.value["vap_all"]

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
      # drma_manual_mode - (optional) is a type of string
      drma_manual_mode = radio_2.value["drma_manual_mode"]
      # override_analysis - (optional) is a type of string
      override_analysis = radio_2.value["override_analysis"]
      # override_band - (optional) is a type of string
      override_band = radio_2.value["override_band"]
      # override_channel - (optional) is a type of string
      override_channel = radio_2.value["override_channel"]
      # override_txpower - (optional) is a type of string
      override_txpower = radio_2.value["override_txpower"]
      # override_vaps - (optional) is a type of string
      override_vaps = radio_2.value["override_vaps"]
      # power_level - (optional) is a type of number
      power_level = radio_2.value["power_level"]
      # radio_id - (optional) is a type of number
      radio_id = radio_2.value["radio_id"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_2.value["spectrum_analysis"]
      # vap_all - (optional) is a type of string
      vap_all = radio_2.value["vap_all"]

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
      # drma_manual_mode - (optional) is a type of string
      drma_manual_mode = radio_3.value["drma_manual_mode"]
      # override_analysis - (optional) is a type of string
      override_analysis = radio_3.value["override_analysis"]
      # override_band - (optional) is a type of string
      override_band = radio_3.value["override_band"]
      # override_channel - (optional) is a type of string
      override_channel = radio_3.value["override_channel"]
      # override_txpower - (optional) is a type of string
      override_txpower = radio_3.value["override_txpower"]
      # override_vaps - (optional) is a type of string
      override_vaps = radio_3.value["override_vaps"]
      # power_level - (optional) is a type of number
      power_level = radio_3.value["power_level"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_3.value["spectrum_analysis"]
      # vap_all - (optional) is a type of string
      vap_all = radio_3.value["vap_all"]

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
      # drma_manual_mode - (optional) is a type of string
      drma_manual_mode = radio_4.value["drma_manual_mode"]
      # override_analysis - (optional) is a type of string
      override_analysis = radio_4.value["override_analysis"]
      # override_band - (optional) is a type of string
      override_band = radio_4.value["override_band"]
      # override_channel - (optional) is a type of string
      override_channel = radio_4.value["override_channel"]
      # override_txpower - (optional) is a type of string
      override_txpower = radio_4.value["override_txpower"]
      # override_vaps - (optional) is a type of string
      override_vaps = radio_4.value["override_vaps"]
      # power_level - (optional) is a type of number
      power_level = radio_4.value["power_level"]
      # spectrum_analysis - (optional) is a type of string
      spectrum_analysis = radio_4.value["spectrum_analysis"]
      # vap_all - (optional) is a type of string
      vap_all = radio_4.value["vap_all"]

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
output "admin" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.admin
}

output "allowaccess" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.allowaccess
}

output "apcfg_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.apcfg_profile
}

output "bonjour_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.bonjour_profile
}

output "coordinate_latitude" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.coordinate_latitude
}

output "coordinate_longitude" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.coordinate_longitude
}

output "firmware_provision" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.firmware_provision
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.id
}

output "image_download" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.image_download
}

output "index" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtp.this.index
}

output "ip_fragment_preventing" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.ip_fragment_preventing
}

output "led_state" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.led_state
}

output "location" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.location
}

output "login_passwd_change" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.login_passwd_change
}

output "mesh_bridge_enable" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.mesh_bridge_enable
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.name
}

output "override_allowaccess" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_allowaccess
}

output "override_ip_fragment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_ip_fragment
}

output "override_lan" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_lan
}

output "override_led_state" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_led_state
}

output "override_login_passwd_change" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_login_passwd_change
}

output "override_split_tunnel" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_split_tunnel
}

output "override_wan_port_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.override_wan_port_mode
}

output "region" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.region
}

output "region_x" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.region_x
}

output "region_y" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.region_y
}

output "split_tunneling_acl_local_ap_subnet" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.split_tunneling_acl_local_ap_subnet
}

output "split_tunneling_acl_path" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.split_tunneling_acl_path
}

output "tun_mtu_downlink" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtp.this.tun_mtu_downlink
}

output "tun_mtu_uplink" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wtp.this.tun_mtu_uplink
}

output "uuid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.uuid
}

output "wan_port_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.wan_port_mode
}

output "wtp_id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.wtp_id
}

output "wtp_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtp.this.wtp_mode
}

output "this" {
  value = fortios_wirelesscontroller_wtp.this
}
```

[top](#index)