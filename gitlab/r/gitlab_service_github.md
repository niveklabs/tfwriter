# gitlab_service_github

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
    gitlab = ">= 3.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_service_github" {
  source = "./modules/gitlab/r/gitlab_service_github"

  # project - (required) is a type of string
  project = null
  # repository_url - (required) is a type of string
  repository_url = null
  # static_context - (optional) is a type of bool
  static_context = null
  # token - (required) is a type of string
  token = null
}
```

[top](#index)

### Variables

```terraform
variable "project" {
  description = "(required)"
  type        = string
}

variable "repository_url" {
  description = "(required)"
  type        = string
}

variable "static_context" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "token" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_service_github" "this" {
  project        = var.project
  repository_url = var.repository_url
  static_context = var.static_context
  token          = var.token
}
```

[top](#index)

### Outputs

```terraform
output "active" {
  description = "returns a bool"
  value       = gitlab_service_github.this.active
}

output "created_at" {
  description = "returns a string"
  value       = gitlab_service_github.this.created_at
}

output "id" {
  description = "returns a string"
  value       = gitlab_service_github.this.id
}

output "title" {
  description = "returns a string"
  value       = gitlab_service_github.this.title
}

output "updated_at" {
  description = "returns a string"
  value       = gitlab_service_github.this.updated_at
}

output "this" {
  value = gitlab_service_github.this
}
```

[top](#index)