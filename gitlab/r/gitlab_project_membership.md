# gitlab_project_membership

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
module "gitlab_project_membership" {
  source = "./modules/gitlab/r/gitlab_project_membership"

  # access_level - (required) is a type of string
  access_level = null
  # project_id - (required) is a type of string
  project_id = null
  # user_id - (required) is a type of number
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "access_level" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_membership" "this" {
  access_level = var.access_level
  project_id   = var.project_id
  user_id      = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_membership.this.id
}

output "this" {
  value = gitlab_project_membership.this
}
```

[top](#index)