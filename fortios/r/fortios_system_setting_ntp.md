# fortios_system_setting_ntp

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
module "fortios_system_setting_ntp" {
  source = "./modules/fortios/r/fortios_system_setting_ntp"

  # ntpserver - (optional) is a type of list of string
  ntpserver = []
  # ntpsync - (optional) is a type of string
  ntpsync = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "ntpserver" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ntpsync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_setting_ntp" "this" {
  ntpserver = var.ntpserver
  ntpsync   = var.ntpsync
  type      = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_setting_ntp.this.id
}

output "ntpserver" {
  description = "returns a list of string"
  value       = fortios_system_setting_ntp.this.ntpserver
}

output "ntpsync" {
  description = "returns a string"
  value       = fortios_system_setting_ntp.this.ntpsync
}

output "this" {
  value = fortios_system_setting_ntp.this
}
```

[top](#index)