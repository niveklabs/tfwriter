# boundary_group

[back](../boundary.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    boundary = ">= 1.0.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "boundary_group" {
  source = "./modules/boundary/r/boundary_group"

  # description - (optional) is a type of string
  description = null
  # member_ids - (optional) is a type of set of string
  member_ids = []
  # name - (optional) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The group description."
  type        = string
  default     = null
}

variable "member_ids" {
  description = "(optional) - Resource IDs for group members, these are most likely boundary users."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - The group name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "scope_id" {
  description = "(required) - The scope ID in which the resource is created. Defaults to the provider's `default_scope` if unset."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # member_ids - (optional) is a type of set of string
  member_ids = var.member_ids
  # name - (optional) is a type of string
  name = var.name
  # scope_id - (required) is a type of string
  scope_id = var.scope_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_group.this.id
}

output "this" {
  value = boundary_group.this
}
```

[top](#index)