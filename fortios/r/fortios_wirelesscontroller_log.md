# fortios_wirelesscontroller_log

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
module "fortios_wirelesscontroller_log" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_log"

  # addrgrp_log - (optional) is a type of string
  addrgrp_log = null
  # ble_log - (optional) is a type of string
  ble_log = null
  # clb_log - (optional) is a type of string
  clb_log = null
  # dhcp_starv_log - (optional) is a type of string
  dhcp_starv_log = null
  # led_sched_log - (optional) is a type of string
  led_sched_log = null
  # radio_event_log - (optional) is a type of string
  radio_event_log = null
  # rogue_event_log - (optional) is a type of string
  rogue_event_log = null
  # sta_event_log - (optional) is a type of string
  sta_event_log = null
  # sta_locate_log - (optional) is a type of string
  sta_locate_log = null
  # status - (optional) is a type of string
  status = null
  # wids_log - (optional) is a type of string
  wids_log = null
  # wtp_event_log - (optional) is a type of string
  wtp_event_log = null
}
```

[top](#index)

### Variables

```terraform
variable "addrgrp_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ble_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clb_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_starv_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "led_sched_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radio_event_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rogue_event_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sta_event_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sta_locate_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wids_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wtp_event_log" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_log" "this" {
  addrgrp_log     = var.addrgrp_log
  ble_log         = var.ble_log
  clb_log         = var.clb_log
  dhcp_starv_log  = var.dhcp_starv_log
  led_sched_log   = var.led_sched_log
  radio_event_log = var.radio_event_log
  rogue_event_log = var.rogue_event_log
  sta_event_log   = var.sta_event_log
  sta_locate_log  = var.sta_locate_log
  status          = var.status
  wids_log        = var.wids_log
  wtp_event_log   = var.wtp_event_log
}
```

[top](#index)

### Outputs

```terraform
output "addrgrp_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.addrgrp_log
}

output "ble_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.ble_log
}

output "clb_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.clb_log
}

output "dhcp_starv_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.dhcp_starv_log
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.id
}

output "led_sched_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.led_sched_log
}

output "radio_event_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.radio_event_log
}

output "rogue_event_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.rogue_event_log
}

output "sta_event_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.sta_event_log
}

output "sta_locate_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.sta_locate_log
}

output "status" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.status
}

output "wids_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.wids_log
}

output "wtp_event_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_log.this.wtp_event_log
}

output "this" {
  value = fortios_wirelesscontroller_log.this
}
```

[top](#index)