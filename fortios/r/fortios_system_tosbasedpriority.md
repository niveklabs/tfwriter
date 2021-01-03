# fortios_system_tosbasedpriority

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
module "fortios_system_tosbasedpriority" {
  source = "./modules/fortios/r/fortios_system_tosbasedpriority"

  # fosid - (optional) is a type of number
  fosid = null
  # priority - (optional) is a type of string
  priority = null
  # tos - (optional) is a type of number
  tos = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_tosbasedpriority" "this" {
  fosid    = var.fosid
  priority = var.priority
  tos      = var.tos
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_system_tosbasedpriority.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_tosbasedpriority.this.id
}

output "priority" {
  description = "returns a string"
  value       = fortios_system_tosbasedpriority.this.priority
}

output "tos" {
  description = "returns a number"
  value       = fortios_system_tosbasedpriority.this.tos
}

output "this" {
  value = fortios_system_tosbasedpriority.this
}
```

[top](#index)