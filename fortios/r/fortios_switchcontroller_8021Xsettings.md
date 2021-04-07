# fortios_switchcontroller_8021Xsettings

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
module "fortios_switchcontroller_8021Xsettings" {
  source = "./modules/fortios/r/fortios_switchcontroller_8021Xsettings"

  # link_down_auth - (optional) is a type of string
  link_down_auth = null
  # max_reauth_attempt - (optional) is a type of number
  max_reauth_attempt = null
  # reauth_period - (optional) is a type of number
  reauth_period = null
  # tx_period - (optional) is a type of number
  tx_period = null
}
```

[top](#index)

### Variables

```terraform
variable "link_down_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_reauth_attempt" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reauth_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tx_period" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_8021Xsettings" "this" {
  # link_down_auth - (optional) is a type of string
  link_down_auth = var.link_down_auth
  # max_reauth_attempt - (optional) is a type of number
  max_reauth_attempt = var.max_reauth_attempt
  # reauth_period - (optional) is a type of number
  reauth_period = var.reauth_period
  # tx_period - (optional) is a type of number
  tx_period = var.tx_period
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_8021Xsettings.this.id
}

output "link_down_auth" {
  description = "returns a string"
  value       = fortios_switchcontroller_8021Xsettings.this.link_down_auth
}

output "max_reauth_attempt" {
  description = "returns a number"
  value       = fortios_switchcontroller_8021Xsettings.this.max_reauth_attempt
}

output "reauth_period" {
  description = "returns a number"
  value       = fortios_switchcontroller_8021Xsettings.this.reauth_period
}

output "tx_period" {
  description = "returns a number"
  value       = fortios_switchcontroller_8021Xsettings.this.tx_period
}

output "this" {
  value = fortios_switchcontroller_8021Xsettings.this
}
```

[top](#index)