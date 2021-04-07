# azuread_group

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/azuread/r/azuread_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # members - (optional) is a type of set of string
  members = []
  # name - (optional) is a type of string
  name = null
  # owners - (optional) is a type of set of string
  owners = []
  # prevent_duplicate_names - (optional) is a type of bool
  prevent_duplicate_names = null
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

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "members" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owners" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "prevent_duplicate_names" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuread_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # members - (optional) is a type of set of string
  members = var.members
  # name - (optional) is a type of string
  name = var.name
  # owners - (optional) is a type of set of string
  owners = var.owners
  # prevent_duplicate_names - (optional) is a type of bool
  prevent_duplicate_names = var.prevent_duplicate_names
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = azuread_group.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azuread_group.this.id
}

output "mail_enabled" {
  description = "returns a bool"
  value       = azuread_group.this.mail_enabled
}

output "members" {
  description = "returns a set of string"
  value       = azuread_group.this.members
}

output "name" {
  description = "returns a string"
  value       = azuread_group.this.name
}

output "object_id" {
  description = "returns a string"
  value       = azuread_group.this.object_id
}

output "owners" {
  description = "returns a set of string"
  value       = azuread_group.this.owners
}

output "security_enabled" {
  description = "returns a bool"
  value       = azuread_group.this.security_enabled
}

output "this" {
  value = azuread_group.this
}
```

[top](#index)