# gitlab_deploy_key

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
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_deploy_key" {
  source = "./modules/gitlab/r/gitlab_deploy_key"

  # can_push - (optional) is a type of bool
  can_push = null
  # key - (required) is a type of string
  key = null
  # project - (required) is a type of string
  project = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "can_push" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_deploy_key" "this" {
  # can_push - (optional) is a type of bool
  can_push = var.can_push
  # key - (required) is a type of string
  key = var.key
  # project - (required) is a type of string
  project = var.project
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_deploy_key.this.id
}

output "this" {
  value = gitlab_deploy_key.this
}
```

[top](#index)