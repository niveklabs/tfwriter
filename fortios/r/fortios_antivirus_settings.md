# fortios_antivirus_settings

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
module "fortios_antivirus_settings" {
  source = "./modules/fortios/r/fortios_antivirus_settings"

  # default_db - (optional) is a type of string
  default_db = null
  # grayware - (optional) is a type of string
  grayware = null
  # override_timeout - (optional) is a type of number
  override_timeout = null
  # use_extreme_db - (optional) is a type of string
  use_extreme_db = null
}
```

[top](#index)

### Variables

```terraform
variable "default_db" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "grayware" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_extreme_db" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_antivirus_settings" "this" {
  # default_db - (optional) is a type of string
  default_db = var.default_db
  # grayware - (optional) is a type of string
  grayware = var.grayware
  # override_timeout - (optional) is a type of number
  override_timeout = var.override_timeout
  # use_extreme_db - (optional) is a type of string
  use_extreme_db = var.use_extreme_db
}
```

[top](#index)

### Outputs

```terraform
output "default_db" {
  description = "returns a string"
  value       = fortios_antivirus_settings.this.default_db
}

output "grayware" {
  description = "returns a string"
  value       = fortios_antivirus_settings.this.grayware
}

output "id" {
  description = "returns a string"
  value       = fortios_antivirus_settings.this.id
}

output "override_timeout" {
  description = "returns a number"
  value       = fortios_antivirus_settings.this.override_timeout
}

output "use_extreme_db" {
  description = "returns a string"
  value       = fortios_antivirus_settings.this.use_extreme_db
}

output "this" {
  value = fortios_antivirus_settings.this
}
```

[top](#index)