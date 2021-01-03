# prismacloud_user_role

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_user_role" {
  source = "./modules/prismacloud/r/prismacloud_user_role"

  # account_group_ids - (optional) is a type of set of string
  account_group_ids = []
  # associated_users - (optional) is a type of set of string
  associated_users = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # restrict_dismissal_access - (optional) is a type of bool
  restrict_dismissal_access = null
  # role_type - (required) is a type of string
  role_type = null
}
```

[top](#index)

### Variables

```terraform
variable "account_group_ids" {
  description = "(optional) - Accessible account group IDs"
  type        = set(string)
  default     = null
}

variable "associated_users" {
  description = "(optional) - Associated application users which cannot exist in the system without the user role"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the role"
  type        = string
}

variable "restrict_dismissal_access" {
  description = "(optional) - Restrict dismissal access"
  type        = bool
  default     = null
}

variable "role_type" {
  description = "(required) - User role type"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_user_role" "this" {
  account_group_ids         = var.account_group_ids
  associated_users          = var.associated_users
  description               = var.description
  name                      = var.name
  restrict_dismissal_access = var.restrict_dismissal_access
  role_type                 = var.role_type
}
```

[top](#index)

### Outputs

```terraform
output "account_groups" {
  description = "returns a list of object"
  value       = prismacloud_user_role.this.account_groups
}

output "id" {
  description = "returns a string"
  value       = prismacloud_user_role.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_user_role.this.last_modified_by
}

output "last_modified_ts" {
  description = "returns a number"
  value       = prismacloud_user_role.this.last_modified_ts
}

output "role_id" {
  description = "returns a string"
  value       = prismacloud_user_role.this.role_id
}

output "this" {
  value = prismacloud_user_role.this
}
```

[top](#index)