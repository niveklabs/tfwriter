# heroku_pipeline_coupling

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
module "heroku_pipeline_coupling" {
  source = "./modules/heroku/r/heroku_pipeline_coupling"

  # app - (required) is a type of string
  app = null
  # pipeline - (required) is a type of string
  pipeline = null
  # stage - (required) is a type of string
  stage = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "pipeline" {
  description = "(required)"
  type        = string
}

variable "stage" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_pipeline_coupling" "this" {
  # app - (required) is a type of string
  app = var.app
  # pipeline - (required) is a type of string
  pipeline = var.pipeline
  # stage - (required) is a type of string
  stage = var.stage
}
```

[top](#index)

### Outputs

```terraform
output "app_id" {
  description = "returns a string"
  value       = heroku_pipeline_coupling.this.app_id
}

output "id" {
  description = "returns a string"
  value       = heroku_pipeline_coupling.this.id
}

output "this" {
  value = heroku_pipeline_coupling.this
}
```

[top](#index)