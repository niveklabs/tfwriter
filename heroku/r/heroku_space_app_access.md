# heroku_space_app_access

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_space_app_access" {
  source = "./modules/heroku/r/heroku_space_app_access"

  # email - (required) is a type of string
  email = null
  # permissions - (required) is a type of set of string
  permissions = []
  # space - (required) is a type of string
  space = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "(required)"
  type        = set(string)
}

variable "space" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_space_app_access" "this" {
  email       = var.email
  permissions = var.permissions
  space       = var.space
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_space_app_access.this.id
}

output "this" {
  value = heroku_space_app_access.this
}
```

[top](#index)