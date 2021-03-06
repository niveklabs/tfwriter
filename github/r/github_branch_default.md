# github_branch_default

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

### Resource

```terraform
resource "github_branch_default" "this" {
  # branch - (required) is a type of string
  branch = var.branch
  # repository - (required) is a type of string
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = github_branch_default.this.id
}

output "this" {
  value = github_branch_default.this
}
```

[top](#index)