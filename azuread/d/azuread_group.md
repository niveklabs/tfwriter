# azuread_group

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_group" {
  source = "./modules/azuread/d/azuread_group"

  # display_name - (optional) is a type of string
  display_name = null
  # mail_enabled - (optional) is a type of bool
  mail_enabled = null
  # name - (optional) is a type of string
  name = null
  # object_id - (optional) is a type of string
  object_id = null
  # security_enabled - (optional) is a type of bool
  security_enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mail_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuread_group" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # mail_enabled - (optional) is a type of bool
  mail_enabled = var.mail_enabled
  # name - (optional) is a type of string
  name = var.name
  # object_id - (optional) is a type of string
  object_id = var.object_id
  # security_enabled - (optional) is a type of bool
  security_enabled = var.security_enabled
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.azuread_group.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azuread_group.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azuread_group.this.id
}

output "mail_enabled" {
  description = "returns a bool"
  value       = data.azuread_group.this.mail_enabled
}

output "members" {
  description = "returns a list of string"
  value       = data.azuread_group.this.members
}

output "name" {
  description = "returns a string"
  value       = data.azuread_group.this.name
}

output "object_id" {
  description = "returns a string"
  value       = data.azuread_group.this.object_id
}

output "owners" {
  description = "returns a list of string"
  value       = data.azuread_group.this.owners
}

output "security_enabled" {
  description = "returns a bool"
  value       = data.azuread_group.this.security_enabled
}

output "this" {
  value = azuread_group.this
}
```

[top](#index)