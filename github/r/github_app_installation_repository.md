# github_app_installation_repository

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
module "github_app_installation_repository" {
  source = "./modules/github/r/github_app_installation_repository"

  # installation_id - (required) is a type of string
  installation_id = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "installation_id" {
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
resource "github_app_installation_repository" "this" {
  installation_id = var.installation_id
  repository      = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = github_app_installation_repository.this.id
}

output "repo_id" {
  description = "returns a number"
  value       = github_app_installation_repository.this.repo_id
}

output "this" {
  value = github_app_installation_repository.this
}
```

[top](#index)