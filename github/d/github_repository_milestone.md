# github_repository_milestone

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "github_repository_milestone" {
  source = "./modules/github/d/github_repository_milestone"

  # number - (required) is a type of number
  number = null
  # owner - (required) is a type of string
  owner = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "number" {
  description = "(required)"
  type        = number
}

variable "owner" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "github_repository_milestone" "this" {
  number     = var.number
  owner      = var.owner
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.github_repository_milestone.this.description
}

output "due_date" {
  description = "returns a string"
  value       = data.github_repository_milestone.this.due_date
}

output "id" {
  description = "returns a string"
  value       = data.github_repository_milestone.this.id
}

output "state" {
  description = "returns a string"
  value       = data.github_repository_milestone.this.state
}

output "title" {
  description = "returns a string"
  value       = data.github_repository_milestone.this.title
}

output "this" {
  value = github_repository_milestone.this
}
```

[top](#index)