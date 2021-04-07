# heroku_collaborator

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
    heroku = ">= 4.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_collaborator" {
  source = "./modules/heroku/r/heroku_collaborator"

  # app - (required) is a type of string
  app = null
  # email - (required) is a type of string
  email = null
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
```

[top](#index)

### Resource

```terraform
resource "heroku_collaborator" "this" {
  app   = var.app
  email = var.email
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_collaborator.this.id
}

output "this" {
  value = heroku_collaborator.this
}
```

[top](#index)