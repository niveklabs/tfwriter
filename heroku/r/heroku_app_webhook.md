# heroku_app_webhook

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
module "heroku_app_webhook" {
  source = "./modules/heroku/r/heroku_app_webhook"

  # app_id - (required) is a type of string
  app_id = null
  # authorization - (optional) is a type of string
  authorization = null
  # include - (required) is a type of list of string
  include = []
  # level - (required) is a type of string
  level = null
  # secret - (optional) is a type of string
  secret = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "authorization" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include" {
  description = "(required)"
  type        = list(string)
}

variable "level" {
  description = "(required)"
  type        = string
}

variable "secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_app_webhook" "this" {
  app_id        = var.app_id
  authorization = var.authorization
  include       = var.include
  level         = var.level
  secret        = var.secret
  url           = var.url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_app_webhook.this.id
}

output "this" {
  value = heroku_app_webhook.this
}
```

[top](#index)