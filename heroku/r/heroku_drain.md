# heroku_drain

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
module "heroku_drain" {
  source = "./modules/heroku/r/heroku_drain"

  # app - (required) is a type of string
  app = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_drain" "this" {
  app = var.app
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_drain.this.id
}

output "token" {
  description = "returns a string"
  value       = heroku_drain.this.token
}

output "this" {
  value = heroku_drain.this
}
```

[top](#index)