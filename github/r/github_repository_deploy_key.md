# github_repository_deploy_key

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
module "github_repository_deploy_key" {
  source = "./modules/github/r/github_repository_deploy_key"

  # key - (required) is a type of string
  key = null
  # read_only - (optional) is a type of bool
  read_only = null
  # repository - (required) is a type of string
  repository = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "read_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository" {
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
resource "github_repository_deploy_key" "this" {
  key        = var.key
  read_only  = var.read_only
  repository = var.repository
  title      = var.title
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_repository_deploy_key.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_repository_deploy_key.this.id
}

output "this" {
  value = github_repository_deploy_key.this
}
```

[top](#index)