# gitlab_project_share_group

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
module "gitlab_project_share_group" {
  source = "./modules/gitlab/r/gitlab_project_share_group"

  # access_level - (required) is a type of string
  access_level = null
  # group_id - (required) is a type of number
  group_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "access_level" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = number
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_share_group" "this" {
  # access_level - (required) is a type of string
  access_level = var.access_level
  # group_id - (required) is a type of number
  group_id = var.group_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_share_group.this.id
}

output "this" {
  value = gitlab_project_share_group.this
}
```

[top](#index)