# github_repository_milestone

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
module "github_repository_milestone" {
  source = "./modules/github/r/github_repository_milestone"

  # description - (optional) is a type of string
  description = null
  # due_date - (optional) is a type of string
  due_date = null
  # owner - (required) is a type of string
  owner = null
  # repository - (required) is a type of string
  repository = null
  # state - (optional) is a type of string
  state = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "due_date" {
  description = "(optional) - in yyyy-mm-dd format"
  type        = string
  default     = null
}

variable "owner" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_repository_milestone" "this" {
  description = var.description
  due_date    = var.due_date
  owner       = var.owner
  repository  = var.repository
  state       = var.state
  title       = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = github_repository_milestone.this.id
}

output "number" {
  description = "returns a number"
  value       = github_repository_milestone.this.number
}

output "this" {
  value = github_repository_milestone.this
}
```

[top](#index)