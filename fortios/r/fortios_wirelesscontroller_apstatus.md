# fortios_wirelesscontroller_apstatus

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
module "fortios_wirelesscontroller_apstatus" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_apstatus"

  # bssid - (optional) is a type of string
  bssid = null
  # fosid - (optional) is a type of number
  fosid = null
  # ssid - (optional) is a type of string
  ssid = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "bssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_apstatus" "this" {
  # bssid - (optional) is a type of string
  bssid = var.bssid
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # ssid - (optional) is a type of string
  ssid = var.ssid
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "bssid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apstatus.this.bssid
}

output "fosid" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_apstatus.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apstatus.this.id
}

output "ssid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apstatus.this.ssid
}

output "status" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apstatus.this.status
}

output "this" {
  value = fortios_wirelesscontroller_apstatus.this
}
```

[top](#index)