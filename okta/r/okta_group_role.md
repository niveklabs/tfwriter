# okta_group_role

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_group_role" {
  source = "./modules/okta/r/okta_group_role"

  # group_id - (required) is a type of string
  group_id = null
  # role_type - (required) is a type of string
  role_type = null
  # target_app_list - (optional) is a type of set of string
  target_app_list = []
  # target_group_list - (optional) is a type of set of string
  target_group_list = []
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - ID of group to attach admin roles to"
  type        = string
}

variable "role_type" {
  description = "(required) - Type of Role to assign"
  type        = string
}

variable "target_app_list" {
  description = "(optional) - List of apps ids for the targets of the admin role."
  type        = set(string)
  default     = null
}

variable "target_group_list" {
  description = "(optional) - List of groups ids for the targets of the admin role."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_group_role" "this" {
  # group_id - (required) is a type of string
  group_id = var.group_id
  # role_type - (required) is a type of string
  role_type = var.role_type
  # target_app_list - (optional) is a type of set of string
  target_app_list = var.target_app_list
  # target_group_list - (optional) is a type of set of string
  target_group_list = var.target_group_list
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_group_role.this.id
}

output "this" {
  value = okta_group_role.this
}
```

[top](#index)