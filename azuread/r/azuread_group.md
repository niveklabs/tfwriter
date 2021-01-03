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
    azuread = ">= 1.1.1"
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
  # members - (optional) is a type of set of string
  members = []
  # name - (required) is a type of string
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

variable "members" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
  description             = var.description
  members                 = var.members
  name                    = var.name
  owners                  = var.owners
  prevent_duplicate_names = var.prevent_duplicate_names
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuread_group.this.id
}

output "members" {
  description = "returns a set of string"
  value       = azuread_group.this.members
}

output "object_id" {
  description = "returns a string"
  value       = azuread_group.this.object_id
}

output "owners" {
  description = "returns a set of string"
  value       = azuread_group.this.owners
}

output "this" {
  value = azuread_group.this
}
```

[top](#index)