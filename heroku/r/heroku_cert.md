# heroku_cert

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
module "heroku_cert" {
  source = "./modules/heroku/r/heroku_cert"

  # app - (required) is a type of string
  app = null
  # certificate_chain - (required) is a type of string
  certificate_chain = null
  # private_key - (required) is a type of string
  private_key = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "certificate_chain" {
  description = "(required)"
  type        = string
}

variable "private_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_cert" "this" {
  app               = var.app
  certificate_chain = var.certificate_chain
  private_key       = var.private_key
}
```

[top](#index)

### Outputs

```terraform
output "cname" {
  description = "returns a string"
  value       = heroku_cert.this.cname
}

output "id" {
  description = "returns a string"
  value       = heroku_cert.this.id
}

output "name" {
  description = "returns a string"
  value       = heroku_cert.this.name
}

output "this" {
  value = heroku_cert.this
}
```

[top](#index)