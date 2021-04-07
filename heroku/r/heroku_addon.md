# heroku_addon

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
module "heroku_addon" {
  source = "./modules/heroku/r/heroku_addon"

  # app - (required) is a type of string
  app = null
  # config - (optional) is a type of map of string
  config = {}
  # name - (optional) is a type of string
  name = null
  # plan - (required) is a type of string
  plan = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "plan" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_addon" "this" {
  # app - (required) is a type of string
  app = var.app
  # config - (optional) is a type of map of string
  config = var.config
  # name - (optional) is a type of string
  name = var.name
  # plan - (required) is a type of string
  plan = var.plan
}
```

[top](#index)

### Outputs

```terraform
output "config_vars" {
  description = "returns a list of string"
  value       = heroku_addon.this.config_vars
}

output "id" {
  description = "returns a string"
  value       = heroku_addon.this.id
}

output "name" {
  description = "returns a string"
  value       = heroku_addon.this.name
}

output "provider_id" {
  description = "returns a string"
  value       = heroku_addon.this.provider_id
}

output "this" {
  value = heroku_addon.this
}
```

[top](#index)