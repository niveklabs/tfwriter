# gitlab_pipeline_schedule_variable

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_pipeline_schedule_variable" {
  source = "./modules/gitlab/r/gitlab_pipeline_schedule_variable"

  # key - (required) is a type of string
  key = null
  # pipeline_schedule_id - (required) is a type of number
  pipeline_schedule_id = null
  # project - (required) is a type of string
  project = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "pipeline_schedule_id" {
  description = "(required)"
  type        = number
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_pipeline_schedule_variable" "this" {
  key                  = var.key
  pipeline_schedule_id = var.pipeline_schedule_id
  project              = var.project
  value                = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_pipeline_schedule_variable.this.id
}

output "this" {
  value = gitlab_pipeline_schedule_variable.this
}
```

[top](#index)