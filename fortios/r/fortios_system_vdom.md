# fortios_system_vdom

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
module "fortios_system_vdom" {
  source = "./modules/fortios/r/fortios_system_vdom"

  # flag - (optional) is a type of number
  flag = null
  # name - (optional) is a type of string
  name = null
  # short_name - (optional) is a type of string
  short_name = null
  # temporary - (optional) is a type of number
  temporary = null
  # vcluster_id - (optional) is a type of number
  vcluster_id = null
}
```

[top](#index)

### Variables

```terraform
variable "flag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "short_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "temporary" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vcluster_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdom" "this" {
  # flag - (optional) is a type of number
  flag = var.flag
  # name - (optional) is a type of string
  name = var.name
  # short_name - (optional) is a type of string
  short_name = var.short_name
  # temporary - (optional) is a type of number
  temporary = var.temporary
  # vcluster_id - (optional) is a type of number
  vcluster_id = var.vcluster_id
}
```

[top](#index)

### Outputs

```terraform
output "flag" {
  description = "returns a number"
  value       = fortios_system_vdom.this.flag
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vdom.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_vdom.this.name
}

output "short_name" {
  description = "returns a string"
  value       = fortios_system_vdom.this.short_name
}

output "temporary" {
  description = "returns a number"
  value       = fortios_system_vdom.this.temporary
}

output "vcluster_id" {
  description = "returns a number"
  value       = fortios_system_vdom.this.vcluster_id
}

output "this" {
  value = fortios_system_vdom.this
}
```

[top](#index)