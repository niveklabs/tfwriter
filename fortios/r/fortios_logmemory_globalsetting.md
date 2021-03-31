# fortios_logmemory_globalsetting

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
module "fortios_logmemory_globalsetting" {
  source = "./modules/fortios/r/fortios_logmemory_globalsetting"

  # full_final_warning_threshold - (optional) is a type of number
  full_final_warning_threshold = null
  # full_first_warning_threshold - (optional) is a type of number
  full_first_warning_threshold = null
  # full_second_warning_threshold - (optional) is a type of number
  full_second_warning_threshold = null
  # max_size - (optional) is a type of number
  max_size = null
}
```

[top](#index)

### Variables

```terraform
variable "full_final_warning_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "full_first_warning_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "full_second_warning_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_size" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logmemory_globalsetting" "this" {
  full_final_warning_threshold  = var.full_final_warning_threshold
  full_first_warning_threshold  = var.full_first_warning_threshold
  full_second_warning_threshold = var.full_second_warning_threshold
  max_size                      = var.max_size
}
```

[top](#index)

### Outputs

```terraform
output "full_final_warning_threshold" {
  description = "returns a number"
  value       = fortios_logmemory_globalsetting.this.full_final_warning_threshold
}

output "full_first_warning_threshold" {
  description = "returns a number"
  value       = fortios_logmemory_globalsetting.this.full_first_warning_threshold
}

output "full_second_warning_threshold" {
  description = "returns a number"
  value       = fortios_logmemory_globalsetting.this.full_second_warning_threshold
}

output "id" {
  description = "returns a string"
  value       = fortios_logmemory_globalsetting.this.id
}

output "max_size" {
  description = "returns a number"
  value       = fortios_logmemory_globalsetting.this.max_size
}

output "this" {
  value = fortios_logmemory_globalsetting.this
}
```

[top](#index)