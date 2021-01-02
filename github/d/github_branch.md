# github_branch

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
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_branch" {
  source = "./modules/github/d/github_branch"

  # branch - (required) is a type of string
  branch = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "branch" {
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
data "github_branch" "this" {
  branch     = var.branch
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = data.github_branch.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.github_branch.this.id
}

output "ref" {
  description = "returns a string"
  value       = data.github_branch.this.ref
}

output "sha" {
  description = "returns a string"
  value       = data.github_branch.this.sha
}

output "this" {
  value = github_branch.this
}
```

[top](#index)