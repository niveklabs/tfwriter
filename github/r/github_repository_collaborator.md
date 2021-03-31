# github_repository_collaborator

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
module "github_repository_collaborator" {
  source = "./modules/github/r/github_repository_collaborator"

  # permission - (optional) is a type of string
  permission = null
  # permission_diff_suppression - (optional) is a type of bool
  permission_diff_suppression = null
  # repository - (required) is a type of string
  repository = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "permission" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permission_diff_suppression" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_repository_collaborator" "this" {
  permission                  = var.permission
  permission_diff_suppression = var.permission_diff_suppression
  repository                  = var.repository
  username                    = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = github_repository_collaborator.this.id
}

output "invitation_id" {
  description = "returns a string"
  value       = github_repository_collaborator.this.invitation_id
}

output "this" {
  value = github_repository_collaborator.this
}
```

[top](#index)