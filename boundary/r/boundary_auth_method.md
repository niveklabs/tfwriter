# boundary_auth_method

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
    boundary = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "boundary_auth_method" {
  source = "./modules/boundary/r/boundary_auth_method"

  # description - (optional) is a type of string
  description = null
  # min_login_name_length - (optional) is a type of number
  min_login_name_length = null
  # min_password_length - (optional) is a type of number
  min_password_length = null
  # name - (optional) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The auth method description."
  type        = string
  default     = null
}

variable "min_login_name_length" {
  description = "(optional) - The minimum login name length."
  type        = number
  default     = null
}

variable "min_password_length" {
  description = "(optional) - The minimum password length."
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - The auth method name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "scope_id" {
  description = "(required) - The scope ID."
  type        = string
}

variable "type" {
  description = "(required) - The resource type."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_auth_method" "this" {
  description           = var.description
  min_login_name_length = var.min_login_name_length
  min_password_length   = var.min_password_length
  name                  = var.name
  scope_id              = var.scope_id
  type                  = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_auth_method.this.id
}

output "min_login_name_length" {
  description = "returns a number"
  value       = boundary_auth_method.this.min_login_name_length
}

output "min_password_length" {
  description = "returns a number"
  value       = boundary_auth_method.this.min_password_length
}

output "this" {
  value = boundary_auth_method.this
}
```

[top](#index)