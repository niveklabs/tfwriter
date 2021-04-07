# aviatrix_rbac_group_permission_attachment

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
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_rbac_group_permission_attachment" {
  source = "./modules/aviatrix/r/aviatrix_rbac_group_permission_attachment"

  # group_name - (required) is a type of string
  group_name = null
  # permission_name - (required) is a type of string
  permission_name = null
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required) - RBAC permission group name."
  type        = string
}

variable "permission_name" {
  description = "(required) - Permission name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_rbac_group_permission_attachment" "this" {
  # group_name - (required) is a type of string
  group_name = var.group_name
  # permission_name - (required) is a type of string
  permission_name = var.permission_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_rbac_group_permission_attachment.this.id
}

output "this" {
  value = aviatrix_rbac_group_permission_attachment.this
}
```

[top](#index)