# gitlab_deploy_key_enable

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
module "gitlab_deploy_key_enable" {
  source = "./modules/gitlab/r/gitlab_deploy_key_enable"

  # can_push - (optional) is a type of bool
  can_push = null
  # key - (optional) is a type of string
  key = null
  # key_id - (required) is a type of string
  key_id = null
  # project - (required) is a type of string
  project = null
  # title - (optional) is a type of string
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_deploy_key_enable" "this" {
  can_push = var.can_push
  key      = var.key
  key_id   = var.key_id
  project  = var.project
  title    = var.title
}
```

[top](#index)

### Outputs

```terraform
output "can_push" {
  description = "returns a bool"
  value       = gitlab_deploy_key_enable.this.can_push
}

output "id" {
  description = "returns a string"
  value       = gitlab_deploy_key_enable.this.id
}

output "key" {
  description = "returns a string"
  value       = gitlab_deploy_key_enable.this.key
}

output "title" {
  description = "returns a string"
  value       = gitlab_deploy_key_enable.this.title
}

output "this" {
  value = gitlab_deploy_key_enable.this
}
```

[top](#index)