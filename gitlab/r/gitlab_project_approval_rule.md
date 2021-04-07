# gitlab_project_approval_rule

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
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_project_approval_rule" {
  source = "./modules/gitlab/r/gitlab_project_approval_rule"

  # approvals_required - (required) is a type of number
  approvals_required = null
  # group_ids - (optional) is a type of set of number
  group_ids = []
  # name - (required) is a type of string
  name = null
  # project - (required) is a type of string
  project = null
  # user_ids - (optional) is a type of set of number
  user_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "approvals_required" {
  description = "(required)"
  type        = number
}

variable "group_ids" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "user_ids" {
  description = "(optional)"
  type        = set(number)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_approval_rule" "this" {
  approvals_required = var.approvals_required
  group_ids          = var.group_ids
  name               = var.name
  project            = var.project
  user_ids           = var.user_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_approval_rule.this.id
}

output "this" {
  value = gitlab_project_approval_rule.this
}
```

[top](#index)