# fortios_system_dscpbasedpriority

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
module "fortios_system_dscpbasedpriority" {
  source = "./modules/fortios/r/fortios_system_dscpbasedpriority"

  # ds - (optional) is a type of number
  ds = null
  # fosid - (optional) is a type of number
  fosid = null
  # priority - (optional) is a type of string
  priority = null
}
```

[top](#index)

### Variables

```terraform
variable "ds" {
  description = "(optional)"
  type        = number
  default     = null
}

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
```

[top](#index)

### Resource

```terraform
resource "fortios_system_dscpbasedpriority" "this" {
  ds       = var.ds
  fosid    = var.fosid
  priority = var.priority
}
```

[top](#index)

### Outputs

```terraform
output "ds" {
  description = "returns a number"
  value       = fortios_system_dscpbasedpriority.this.ds
}

output "fosid" {
  description = "returns a number"
  value       = fortios_system_dscpbasedpriority.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_dscpbasedpriority.this.id
}

output "priority" {
  description = "returns a string"
  value       = fortios_system_dscpbasedpriority.this.priority
}

output "this" {
  value = fortios_system_dscpbasedpriority.this
}
```

[top](#index)