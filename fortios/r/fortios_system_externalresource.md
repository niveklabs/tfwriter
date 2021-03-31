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
    fortios = ">= 1.11.0"
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
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # refresh_rate - (required) is a type of number
  refresh_rate = null
  # resource - (required) is a type of string
  resource = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # user_agent - (optional) is a type of string
  user_agent = null
  # username - (optional) is a type of string
  username = null
  # uuid - (optional) is a type of string
  uuid = null
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

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
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

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "user_agent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_externalresource" "this" {
  category                = var.category
  comments                = var.comments
  interface               = var.interface
  interface_select_method = var.interface_select_method
  name                    = var.name
  password                = var.password
  refresh_rate            = var.refresh_rate
  resource                = var.resource
  source_ip               = var.source_ip
  status                  = var.status
  type                    = var.type
  user_agent              = var.user_agent
  username                = var.username
  uuid                    = var.uuid
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

output "interface" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.interface_select_method
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.source_ip
}

output "status" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.status
}

output "type" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.type
}

output "user_agent" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.user_agent
}

output "username" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.username
}

output "uuid" {
  description = "returns a string"
  value       = fortios_system_externalresource.this.uuid
}

output "this" {
  value = fortios_system_externalresource.this
}
```

[top](#index)