# fortios_switchcontrollerqos_dot1pmap

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
module "fortios_switchcontrollerqos_dot1pmap" {
  source = "./modules/fortios/r/fortios_switchcontrollerqos_dot1pmap"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # priority_0 - (optional) is a type of string
  priority_0 = null
  # priority_1 - (optional) is a type of string
  priority_1 = null
  # priority_2 - (optional) is a type of string
  priority_2 = null
  # priority_3 - (optional) is a type of string
  priority_3 = null
  # priority_4 - (optional) is a type of string
  priority_4 = null
  # priority_5 - (optional) is a type of string
  priority_5 = null
  # priority_6 - (optional) is a type of string
  priority_6 = null
  # priority_7 - (optional) is a type of string
  priority_7 = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority_0" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_7" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerqos_dot1pmap" "this" {
  description = var.description
  name        = var.name
  priority_0  = var.priority_0
  priority_1  = var.priority_1
  priority_2  = var.priority_2
  priority_3  = var.priority_3
  priority_4  = var.priority_4
  priority_5  = var.priority_5
  priority_6  = var.priority_6
  priority_7  = var.priority_7
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.id
}

output "priority_0" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_0
}

output "priority_1" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_1
}

output "priority_2" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_2
}

output "priority_3" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_3
}

output "priority_4" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_4
}

output "priority_5" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_5
}

output "priority_6" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_6
}

output "priority_7" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_dot1pmap.this.priority_7
}

output "this" {
  value = fortios_switchcontrollerqos_dot1pmap.this
}
```

[top](#index)