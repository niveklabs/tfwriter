# heroku_pipeline_config_var

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
module "heroku_pipeline_config_var" {
  source = "./modules/heroku/r/heroku_pipeline_config_var"

  # pipeline_id - (required) is a type of string
  pipeline_id = null
  # pipeline_stage - (required) is a type of string
  pipeline_stage = null
  # sensitive_vars - (optional) is a type of map of string
  sensitive_vars = {}
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "pipeline_id" {
  description = "(required)"
  type        = string
}

variable "pipeline_stage" {
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
resource "heroku_pipeline_config_var" "this" {
  pipeline_id    = var.pipeline_id
  pipeline_stage = var.pipeline_stage
  sensitive_vars = var.sensitive_vars
  vars           = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "all_vars" {
  description = "returns a map of string"
  value       = heroku_pipeline_config_var.this.all_vars
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = heroku_pipeline_config_var.this.id
}

output "this" {
  value = heroku_pipeline_config_var.this
}
```

[top](#index)