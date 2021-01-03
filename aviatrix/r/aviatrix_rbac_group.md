# aviatrix_rbac_group

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_rbac_group" {
  source = "./modules/aviatrix/r/aviatrix_rbac_group"

  # group_name - (required) is a type of string
  group_name = null
  # local_login - (optional) is a type of bool
  local_login = null
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required) - RBAC permission group name."
  type        = string
}

variable "local_login" {
  description = "(optional) - Whether to allow members of an RBAC group to bypass LDAP/MFA for Duo login"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_rbac_group" "this" {
  group_name  = var.group_name
  local_login = var.local_login
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_rbac_group.this.id
}

output "this" {
  value = aviatrix_rbac_group.this
}
```

[top](#index)