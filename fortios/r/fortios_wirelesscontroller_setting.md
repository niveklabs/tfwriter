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
    fortios = ">= 1.6.18"
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
  # duplicate_ssid - (optional) is a type of string
  duplicate_ssid = null
  # fake_ssid_action - (optional) is a type of string
  fake_ssid_action = null
  # fapc_compatibility - (optional) is a type of string
  fapc_compatibility = null
  # phishing_ssid_detect - (optional) is a type of string
  phishing_ssid_detect = null

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

variable "duplicate_ssid" {
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
  account_id           = var.account_id
  country              = var.country
  duplicate_ssid       = var.duplicate_ssid
  fake_ssid_action     = var.fake_ssid_action
  fapc_compatibility   = var.fapc_compatibility
  phishing_ssid_detect = var.phishing_ssid_detect

  dynamic "offending_ssid" {
    for_each = var.offending_ssid
    content {
      action       = offending_ssid.value["action"]
      id           = offending_ssid.value["id"]
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

output "this" {
  value = fortios_wirelesscontroller_setting.this
}
```

[top](#index)