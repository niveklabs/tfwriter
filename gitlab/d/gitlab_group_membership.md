# gitlab_group_membership

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "gitlab_group_membership" {
  source = "./modules/gitlab/d/gitlab_group_membership"

  # access_level - (optional) is a type of string
  access_level = null
  # full_path - (optional) is a type of string
  full_path = null
  # group_id - (optional) is a type of number
  group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "access_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "gitlab_group_membership" "this" {
  access_level = var.access_level
  full_path    = var.full_path
  group_id     = var.group_id
}
```

[top](#index)

### Outputs

```terraform
output "access_level" {
  description = "returns a string"
  value       = data.gitlab_group_membership.this.access_level
}

output "full_path" {
  description = "returns a string"
  value       = data.gitlab_group_membership.this.full_path
}

output "group_id" {
  description = "returns a number"
  value       = data.gitlab_group_membership.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.gitlab_group_membership.this.id
}

output "members" {
  description = "returns a list of object"
  value       = data.gitlab_group_membership.this.members
}

output "this" {
  value = gitlab_group_membership.this
}
```

[top](#index)