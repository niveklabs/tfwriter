# heroku_domain

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
module "heroku_domain" {
  source = "./modules/heroku/r/heroku_domain"

  # app - (required) is a type of string
  app = null
  # hostname - (required) is a type of string
  hostname = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "hostname" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_domain" "this" {
  app      = var.app
  hostname = var.hostname
}
```

[top](#index)

### Outputs

```terraform
output "cname" {
  description = "returns a string"
  value       = heroku_domain.this.cname
}

output "id" {
  description = "returns a string"
  value       = heroku_domain.this.id
}

output "this" {
  value = heroku_domain.this
}
```

[top](#index)