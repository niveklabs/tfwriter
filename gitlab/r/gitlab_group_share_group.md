# gitlab_group_share_group

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
module "gitlab_group_share_group" {
  source = "./modules/gitlab/r/gitlab_group_share_group"

  # expires_at - (optional) is a type of string
  expires_at = null
  # group_access - (required) is a type of string
  group_access = null
  # group_id - (required) is a type of string
  group_id = null
  # share_group_id - (required) is a type of number
  share_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "expires_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_access" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "share_group_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_group_share_group" "this" {
  expires_at     = var.expires_at
  group_access   = var.group_access
  group_id       = var.group_id
  share_group_id = var.share_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_group_share_group.this.id
}

output "this" {
  value = gitlab_group_share_group.this
}
```

[top](#index)