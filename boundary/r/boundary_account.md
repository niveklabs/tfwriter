# boundary_account

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
module "boundary_account" {
  source = "./modules/boundary/r/boundary_account"

  # auth_method_id - (required) is a type of string
  auth_method_id = null
  # description - (optional) is a type of string
  description = null
  # login_name - (optional) is a type of string
  login_name = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_method_id" {
  description = "(required) - The resource ID for the auth method."
  type        = string
}

variable "description" {
  description = "(optional) - The account description."
  type        = string
  default     = null
}

variable "login_name" {
  description = "(optional) - The login name for this account."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The account name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - The account password."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The resource type."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_account" "this" {
  auth_method_id = var.auth_method_id
  description    = var.description
  login_name     = var.login_name
  name           = var.name
  password       = var.password
  type           = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_account.this.id
}

output "this" {
  value = boundary_account.this
}
```

[top](#index)