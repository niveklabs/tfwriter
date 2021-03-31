# boundary_user

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
module "boundary_user" {
  source = "./modules/boundary/r/boundary_user"

  # account_ids - (optional) is a type of set of string
  account_ids = []
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_ids" {
  description = "(optional) - Account ID's to associate with this user resource."
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - The user description."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The username. Defaults to the resource name."
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
resource "boundary_user" "this" {
  account_ids = var.account_ids
  description = var.description
  name        = var.name
  scope_id    = var.scope_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_user.this.id
}

output "this" {
  value = boundary_user.this
}
```

[top](#index)