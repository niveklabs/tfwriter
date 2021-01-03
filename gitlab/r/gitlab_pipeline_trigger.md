# gitlab_pipeline_trigger

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
module "gitlab_pipeline_trigger" {
  source = "./modules/gitlab/r/gitlab_pipeline_trigger"

  # description - (required) is a type of string
  description = null
  # project - (required) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_pipeline_trigger" "this" {
  description = var.description
  project     = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_pipeline_trigger.this.id
}

output "token" {
  description = "returns a string"
  value       = gitlab_pipeline_trigger.this.token
}

output "this" {
  value = gitlab_pipeline_trigger.this
}
```

[top](#index)