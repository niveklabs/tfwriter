# boundary_scope

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
module "boundary_scope" {
  source = "./modules/boundary/r/boundary_scope"

  # auto_create_admin_role - (optional) is a type of bool
  auto_create_admin_role = null
  # auto_create_default_role - (optional) is a type of bool
  auto_create_default_role = null
  # description - (optional) is a type of string
  description = null
  # global_scope - (optional) is a type of bool
  global_scope = null
  # name - (optional) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_create_admin_role" {
  description = "(optional) - If set, when a new scope is created, the provider will not disable the functionality that automatically creates a role in the new scope and gives permissions to manage the scope to the provider's user. Marking this true makes for simpler HCL but results in role resources that are unmanaged by Terraform."
  type        = bool
  default     = null
}

variable "auto_create_default_role" {
  description = "(optional) - Only relevant when creating an org scope. If set, when a new scope is created, the provider will not disable the functionality that automatically creates a role in the new scope and gives listing of scopes and auth methods and the ability to authenticate to the anonymous user. Marking this true makes for simpler HCL but results in role resources that are unmanaged by Terraform."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The scope description."
  type        = string
  default     = null
}

variable "global_scope" {
  description = "(optional) - Indicates that the scope containing this value is the global scope, which triggers some specialized behavior to allow it to be imported and managed."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - The scope name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "scope_id" {
  description = "(required) - The scope ID containing the sub scope resource."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_scope" "this" {
  # auto_create_admin_role - (optional) is a type of bool
  auto_create_admin_role = var.auto_create_admin_role
  # auto_create_default_role - (optional) is a type of bool
  auto_create_default_role = var.auto_create_default_role
  # description - (optional) is a type of string
  description = var.description
  # global_scope - (optional) is a type of bool
  global_scope = var.global_scope
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
  value       = boundary_scope.this.id
}

output "this" {
  value = boundary_scope.this
}
```

[top](#index)