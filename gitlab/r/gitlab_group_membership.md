# gitlab_group_membership

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
module "gitlab_group_membership" {
  source = "./modules/gitlab/r/gitlab_group_membership"

  # access_level - (required) is a type of string
  access_level = null
  # expires_at - (optional) is a type of string
  expires_at = null
  # group_id - (required) is a type of string
  group_id = null
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

variable "expires_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
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
resource "gitlab_group_membership" "this" {
  # access_level - (required) is a type of string
  access_level = var.access_level
  # expires_at - (optional) is a type of string
  expires_at = var.expires_at
  # group_id - (required) is a type of string
  group_id = var.group_id
  # user_id - (required) is a type of number
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_group_membership.this.id
}

output "this" {
  value = gitlab_group_membership.this
}
```

[top](#index)