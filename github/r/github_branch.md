# github_branch

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "github_branch" {
  source = "./modules/github/r/github_branch"

  # branch - (required) is a type of string
  branch = null
  # repository - (required) is a type of string
  repository = null
  # source_branch - (optional) is a type of string
  source_branch = null
  # source_sha - (optional) is a type of string
  source_sha = null
}
```

[top](#index)

### Variables

```hcl
variable "branch" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "source_branch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_sha" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "github_branch" "this" {
  branch        = var.branch
  repository    = var.repository
  source_branch = var.source_branch
  source_sha    = var.source_sha
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_branch.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_branch.this.id
}

output "ref" {
  description = "returns a string"
  value       = github_branch.this.ref
}

output "sha" {
  description = "returns a string"
  value       = github_branch.this.sha
}

output "source_sha" {
  description = "returns a string"
  value       = github_branch.this.source_sha
}

output "this" {
  value = github_branch.this
}
```

[top](#index)