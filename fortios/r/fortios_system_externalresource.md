# fortios_system_externalresource

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
module "fortios_system_externalresource" {
  source = "./modules/fortios/r/fortios_system_externalresource"

  # category - (optional) is a type of number
  category = null
  # comments - (optional) is a type of string
  comments = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # refresh_rate - (required) is a type of number
  refresh_rate = null
  # resource - (required) is a type of string
  resource = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refresh_rate" {
  description = "(required)"
  type        = number
}

variable "resource" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_externalresource" "this" {
  category     = var.category
  comments     = var.comments
  name         = var.name
  password     = var.password
  refresh_rate = var.refresh_rate
  resource     = var.resource
  status       = var.status
  type         = var.type
  username     = var.username
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a number"
  value       = fortios_system_externalresource.this.category
}

output "id" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.status
}

output "type" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.type
}

output "username" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.username
}

output "this" {
  value = fortios_system_externalresource.this
}
```

[top](#index)