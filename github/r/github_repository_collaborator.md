# github_repository_collaborator

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "github_repository_collaborator" {
  source = "./modules/github/r/github_repository_collaborator"

  # permission - (optional) is a type of string
  permission = null
  # repository - (required) is a type of string
  repository = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```hcl
variable "permission" {
  description = "(optional)"
  type        = string
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

```hcl
resource "github_repository_collaborator" "this" {
  permission = var.permission
  repository = var.repository
  username   = var.username
}
```

[top](#index)

### Outputs

```hcl
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