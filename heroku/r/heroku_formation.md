# heroku_formation

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
module "heroku_formation" {
  source = "./modules/heroku/r/heroku_formation"

  # app - (required) is a type of string
  app = null
  # quantity - (required) is a type of number
  quantity = null
  # size - (required) is a type of string
  size = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "quantity" {
  description = "(required)"
  type        = number
}

variable "size" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_formation" "this" {
  # app - (required) is a type of string
  app = var.app
  # quantity - (required) is a type of number
  quantity = var.quantity
  # size - (required) is a type of string
  size = var.size
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_formation.this.id
}

output "this" {
  value = heroku_formation.this
}
```

[top](#index)