# boundary_role

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
module "boundary_role" {
  source = "./modules/boundary/r/boundary_role"

  # default_role - (optional) is a type of bool
  default_role = null
  # description - (optional) is a type of string
  description = null
  # grant_scope_id - (optional) is a type of string
  grant_scope_id = null
  # grant_strings - (optional) is a type of set of string
  grant_strings = []
  # name - (optional) is a type of string
  name = null
  # principal_ids - (optional) is a type of set of string
  principal_ids = []
  # scope_id - (required) is a type of string
  scope_id = null
}
```

[top](#index)

### Variables

```terraform
variable "default_role" {
  description = "(optional) - Indicates that the role containing this value is the default role (that is, has the id 'r_default'), which triggers some specialized behavior to allow it to be imported and managed."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The role description."
  type        = string
  default     = null
}

variable "grant_scope_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "grant_strings" {
  description = "(optional) -  A list of stringified grants for the role."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - The role name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "principal_ids" {
  description = "(optional) - A list of principal (user or group) IDs to add as principals on the role."
  type        = set(string)
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
resource "boundary_role" "this" {
  default_role   = var.default_role
  description    = var.description
  grant_scope_id = var.grant_scope_id
  grant_strings  = var.grant_strings
  name           = var.name
  principal_ids  = var.principal_ids
  scope_id       = var.scope_id
}
```

[top](#index)

### Outputs

```terraform
output "grant_scope_id" {
  description = "returns a string"
  value       = boundary_role.this.grant_scope_id
}

output "id" {
  description = "returns a string"
  value       = boundary_role.this.id
}

output "this" {
  value = boundary_role.this
}
```

[top](#index)