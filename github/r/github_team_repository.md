# github_team_repository

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
module "github_team_repository" {
  source = "./modules/github/r/github_team_repository"

  # permission - (optional) is a type of string
  permission = null
  # repository - (required) is a type of string
  repository = null
  # team_id - (required) is a type of string
  team_id = null
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

variable "team_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_team_repository" "this" {
  permission = var.permission
  repository = var.repository
  team_id    = var.team_id
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_team_repository.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_team_repository.this.id
}

output "this" {
  value = github_team_repository.this
}
```

[top](#index)