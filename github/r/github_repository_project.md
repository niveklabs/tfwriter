# github_repository_project

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_repository_project" {
  source = "./modules/github/r/github_repository_project"

  # body - (optional) is a type of string
  body = null
  # name - (required) is a type of string
  name = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_repository_project" "this" {
  # body - (optional) is a type of string
  body = var.body
  # name - (required) is a type of string
  name = var.name
  # repository - (required) is a type of string
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_repository_project.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_repository_project.this.id
}

output "url" {
  description = "returns a string"
  value       = github_repository_project.this.url
}

output "this" {
  value = github_repository_project.this
}
```

[top](#index)