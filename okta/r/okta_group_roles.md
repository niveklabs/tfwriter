# okta_group_roles

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
module "okta_group_roles" {
  source = "./modules/okta/r/okta_group_roles"

  # admin_roles - (optional) is a type of set of string
  admin_roles = []
  # group_id - (required) is a type of string
  group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_roles" {
  description = "(optional) - Admin roles associated with the group. This can also be done per user."
  type        = set(string)
  default     = null
}

variable "group_id" {
  description = "(required) - ID of group to attach admin roles to"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_group_roles" "this" {
  # admin_roles - (optional) is a type of set of string
  admin_roles = var.admin_roles
  # group_id - (required) is a type of string
  group_id = var.group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_group_roles.this.id
}

output "this" {
  value = okta_group_roles.this
}
```

[top](#index)