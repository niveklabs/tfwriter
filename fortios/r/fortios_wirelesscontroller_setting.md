# fortios_wirelesscontroller_setting

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
module "fortios_wirelesscontroller_setting" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_setting"

  # account_id - (optional) is a type of string
  account_id = null
  # country - (optional) is a type of string
  country = null
  # darrp_optimize - (optional) is a type of number
  darrp_optimize = null
  # device_holdoff - (optional) is a type of number
  device_holdoff = null
  # device_idle - (optional) is a type of number
  device_idle = null
  # device_weight - (optional) is a type of number
  device_weight = null
  # duplicate_ssid - (optional) is a type of string
  duplicate_ssid = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fake_ssid_action - (optional) is a type of string
  fake_ssid_action = null
  # fapc_compatibility - (optional) is a type of string
  fapc_compatibility = null
  # phishing_ssid_detect - (optional) is a type of string
  phishing_ssid_detect = null
  # wfa_compatibility - (optional) is a type of string
  wfa_compatibility = null

  darrp_optimize_schedules = [{
    name = null
  }]

  offending_ssid = [{
    action       = null
    id           = null
    ssid_pattern = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "country" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "darrp_optimize" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_holdoff" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_idle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "duplicate_ssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fake_ssid_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fapc_compatibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "phishing_ssid_detect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wfa_compatibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "darrp_optimize_schedules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "offending_ssid" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action       = string
      id           = number
      ssid_pattern = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_setting" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # country - (optional) is a type of string
  country = var.country
  # darrp_optimize - (optional) is a type of number
  darrp_optimize = var.darrp_optimize
  # device_holdoff - (optional) is a type of number
  device_holdoff = var.device_holdoff
  # device_idle - (optional) is a type of number
  device_idle = var.device_idle
  # device_weight - (optional) is a type of number
  device_weight = var.device_weight
  # duplicate_ssid - (optional) is a type of string
  duplicate_ssid = var.duplicate_ssid
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fake_ssid_action - (optional) is a type of string
  fake_ssid_action = var.fake_ssid_action
  # fapc_compatibility - (optional) is a type of string
  fapc_compatibility = var.fapc_compatibility
  # phishing_ssid_detect - (optional) is a type of string
  phishing_ssid_detect = var.phishing_ssid_detect
  # wfa_compatibility - (optional) is a type of string
  wfa_compatibility = var.wfa_compatibility

  dynamic "darrp_optimize_schedules" {
    for_each = var.darrp_optimize_schedules
    content {
      # name - (optional) is a type of string
      name = darrp_optimize_schedules.value["name"]
    }
  }

  dynamic "offending_ssid" {
    for_each = var.offending_ssid
    content {
      # action - (optional) is a type of string
      action = offending_ssid.value["action"]
      # id - (optional) is a type of number
      id = offending_ssid.value["id"]
      # ssid_pattern - (optional) is a type of string
      ssid_pattern = offending_ssid.value["ssid_pattern"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.account_id
}

output "country" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.country
}

output "darrp_optimize" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_setting.this.darrp_optimize
}

output "device_holdoff" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_setting.this.device_holdoff
}

output "device_idle" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_setting.this.device_idle
}

output "device_weight" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_setting.this.device_weight
}

output "duplicate_ssid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.duplicate_ssid
}

output "fake_ssid_action" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.fake_ssid_action
}

output "fapc_compatibility" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.fapc_compatibility
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.id
}

output "phishing_ssid_detect" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.phishing_ssid_detect
}

output "wfa_compatibility" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_setting.this.wfa_compatibility
}

output "this" {
  value = fortios_wirelesscontroller_setting.this
}
```

[top](#index)