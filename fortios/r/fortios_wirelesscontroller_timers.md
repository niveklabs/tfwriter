# fortios_wirelesscontroller_timers

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
module "fortios_wirelesscontroller_timers" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_timers"

  # ble_scan_report_intv - (optional) is a type of number
  ble_scan_report_intv = null
  # client_idle_timeout - (optional) is a type of number
  client_idle_timeout = null
  # darrp_day - (optional) is a type of string
  darrp_day = null
  # darrp_optimize - (optional) is a type of number
  darrp_optimize = null
  # discovery_interval - (optional) is a type of number
  discovery_interval = null
  # drma_interval - (optional) is a type of number
  drma_interval = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # echo_interval - (optional) is a type of number
  echo_interval = null
  # fake_ap_log - (optional) is a type of number
  fake_ap_log = null
  # ipsec_intf_cleanup - (optional) is a type of number
  ipsec_intf_cleanup = null
  # radio_stats_interval - (optional) is a type of number
  radio_stats_interval = null
  # rogue_ap_log - (optional) is a type of number
  rogue_ap_log = null
  # sta_capability_interval - (optional) is a type of number
  sta_capability_interval = null
  # sta_locate_timer - (optional) is a type of number
  sta_locate_timer = null
  # sta_stats_interval - (optional) is a type of number
  sta_stats_interval = null
  # vap_stats_interval - (optional) is a type of number
  vap_stats_interval = null

  darrp_time = [{
    time = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ble_scan_report_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "darrp_day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "darrp_optimize" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "discovery_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "drma_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "echo_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fake_ap_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipsec_intf_cleanup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "radio_stats_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rogue_ap_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sta_capability_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sta_locate_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sta_stats_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vap_stats_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "darrp_time" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      time = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_timers" "this" {
  ble_scan_report_intv    = var.ble_scan_report_intv
  client_idle_timeout     = var.client_idle_timeout
  darrp_day               = var.darrp_day
  darrp_optimize          = var.darrp_optimize
  discovery_interval      = var.discovery_interval
  drma_interval           = var.drma_interval
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  echo_interval           = var.echo_interval
  fake_ap_log             = var.fake_ap_log
  ipsec_intf_cleanup      = var.ipsec_intf_cleanup
  radio_stats_interval    = var.radio_stats_interval
  rogue_ap_log            = var.rogue_ap_log
  sta_capability_interval = var.sta_capability_interval
  sta_locate_timer        = var.sta_locate_timer
  sta_stats_interval      = var.sta_stats_interval
  vap_stats_interval      = var.vap_stats_interval

  dynamic "darrp_time" {
    for_each = var.darrp_time
    content {
      time = darrp_time.value["time"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ble_scan_report_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.ble_scan_report_intv
}

output "client_idle_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.client_idle_timeout
}

output "darrp_day" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_timers.this.darrp_day
}

output "darrp_optimize" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.darrp_optimize
}

output "discovery_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.discovery_interval
}

output "drma_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.drma_interval
}

output "echo_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.echo_interval
}

output "fake_ap_log" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.fake_ap_log
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_timers.this.id
}

output "ipsec_intf_cleanup" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.ipsec_intf_cleanup
}

output "radio_stats_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.radio_stats_interval
}

output "rogue_ap_log" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.rogue_ap_log
}

output "sta_capability_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.sta_capability_interval
}

output "sta_locate_timer" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.sta_locate_timer
}

output "sta_stats_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.sta_stats_interval
}

output "vap_stats_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_timers.this.vap_stats_interval
}

output "this" {
  value = fortios_wirelesscontroller_timers.this
}
```

[top](#index)