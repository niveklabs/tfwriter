# onelogin_roles

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.12"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_roles" {
  source = "./modules/onelogin/r/onelogin_roles"

  # admins - (optional) is a type of set of number
  admins = []
  # apps - (optional) is a type of set of number
  apps = []
  # name - (required) is a type of string
  name = null
  # users - (optional) is a type of set of number
  users = []
}
```

[top](#index)

### Variables

```terraform
variable "admins" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "apps" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "users" {
  description = "(optional)"
  type        = set(number)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_roles" "this" {
  admins = var.admins
  apps   = var.apps
  name   = var.name
  users  = var.users
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = onelogin_roles.this.id
}

output "this" {
  value = onelogin_roles.this
}
```

[top](#index)