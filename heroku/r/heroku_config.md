# heroku_config

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
module "heroku_config" {
  source = "./modules/heroku/r/heroku_config"

  # sensitive_vars - (optional) is a type of map of string
  sensitive_vars = {}
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
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
resource "heroku_config" "this" {
  sensitive_vars = var.sensitive_vars
  vars           = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_config.this.id
}

output "this" {
  value = heroku_config.this
}
```

[top](#index)