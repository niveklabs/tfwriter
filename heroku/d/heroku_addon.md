# heroku_addon

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/heroku/d/heroku_addon"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "heroku_addon" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "app" {
  description = "returns a string"
  value       = data.heroku_addon.this.app
}

output "config_vars" {
  description = "returns a list of string"
  value       = data.heroku_addon.this.config_vars
}

output "id" {
  description = "returns a string"
  value       = data.heroku_addon.this.id
}

output "plan" {
  description = "returns a string"
  value       = data.heroku_addon.this.plan
}

output "provider_id" {
  description = "returns a string"
  value       = data.heroku_addon.this.provider_id
}

output "this" {
  value = heroku_addon.this
}
```

[top](#index)