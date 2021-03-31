# fortios_fmg_system_global

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
module "fortios_fmg_system_global" {
  source = "./modules/fortios/r/fortios_fmg_system_global"

  # adom_mode - (optional) is a type of string
  adom_mode = null
  # adom_status - (optional) is a type of string
  adom_status = null
  # fortianalyzer_status - (optional) is a type of string
  fortianalyzer_status = null
  # hostname - (optional) is a type of string
  hostname = null
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "adom_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "adom_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortianalyzer_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_global" "this" {
  adom_mode            = var.adom_mode
  adom_status          = var.adom_status
  fortianalyzer_status = var.fortianalyzer_status
  hostname             = var.hostname
  timezone             = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_global.this.id
}

output "this" {
  value = fortios_fmg_system_global.this
}
```

[top](#index)