# heroku_account_feature

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
    heroku = ">= 4.1.1-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_account_feature" {
  source = "./modules/heroku/r/heroku_account_feature"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_account_feature" "this" {
  enabled = var.enabled
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = heroku_account_feature.this.description
}

output "id" {
  description = "returns a string"
  value       = heroku_account_feature.this.id
}

output "state" {
  description = "returns a string"
  value       = heroku_account_feature.this.state
}

output "this" {
  value = heroku_account_feature.this
}
```

[top](#index)