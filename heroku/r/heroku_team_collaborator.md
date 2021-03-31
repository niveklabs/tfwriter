# heroku_team_collaborator

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
    heroku = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_team_collaborator" {
  source = "./modules/heroku/r/heroku_team_collaborator"

  # app - (required) is a type of string
  app = null
  # email - (required) is a type of string
  email = null
  # permissions - (required) is a type of set of string
  permissions = []
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "heroku_team_collaborator" "this" {
  app         = var.app
  email       = var.email
  permissions = var.permissions
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_team_collaborator.this.id
}

output "this" {
  value = heroku_team_collaborator.this
}
```

[top](#index)