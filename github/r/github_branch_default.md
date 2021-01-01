# github_branch_default

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
module "github_branch_default" {
  source = "./modules/github/r/github_branch_default"

  # branch - (required) is a type of string
  branch = null
  # repository - (required) is a type of string
  repository = null
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
```

[top](#index)

### Resource

```hcl
resource "github_branch_default" "this" {
  branch     = var.branch
  repository = var.repository
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = github_branch_default.this.id
}

output "this" {
  value = github_branch_default.this
}
```

[top](#index)