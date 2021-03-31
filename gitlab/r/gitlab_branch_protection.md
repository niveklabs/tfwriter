# gitlab_branch_protection

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_branch_protection" {
  source = "./modules/gitlab/r/gitlab_branch_protection"

  # branch - (required) is a type of string
  branch = null
  # code_owner_approval_required - (optional) is a type of bool
  code_owner_approval_required = null
  # merge_access_level - (required) is a type of string
  merge_access_level = null
  # project - (required) is a type of string
  project = null
  # push_access_level - (required) is a type of string
  push_access_level = null
}
```

[top](#index)

### Variables

```terraform
variable "branch" {
  description = "(required)"
  type        = string
}

variable "code_owner_approval_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "merge_access_level" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "push_access_level" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_branch_protection" "this" {
  branch                       = var.branch
  code_owner_approval_required = var.code_owner_approval_required
  merge_access_level           = var.merge_access_level
  project                      = var.project
  push_access_level            = var.push_access_level
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_branch_protection.this.id
}

output "this" {
  value = gitlab_branch_protection.this
}
```

[top](#index)