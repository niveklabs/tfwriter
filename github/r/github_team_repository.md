# github_team_repository

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

```terraform
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
  description = "(required) - ID or slug of team"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_team_repository" "this" {
  permission = var.permission
  repository = var.repository
  team_id    = var.team_id
}
```

[top](#index)

### Outputs

```terraform
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