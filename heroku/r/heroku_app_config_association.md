# heroku_app_config_association

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
module "heroku_app_config_association" {
  source = "./modules/heroku/r/heroku_app_config_association"

  # app_id - (required) is a type of string
  app_id = null
  # sensitive_vars - (optional) is a type of map of string
  sensitive_vars = {}
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "sensitive_vars" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vars" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "heroku_app_config_association" "this" {
  app_id         = var.app_id
  sensitive_vars = var.sensitive_vars
  vars           = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_app_config_association.this.id
}

output "this" {
  value = heroku_app_config_association.this
}
```

[top](#index)