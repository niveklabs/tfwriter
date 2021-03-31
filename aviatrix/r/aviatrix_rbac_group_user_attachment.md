# aviatrix_rbac_group_user_attachment

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
module "aviatrix_rbac_group_user_attachment" {
  source = "./modules/aviatrix/r/aviatrix_rbac_group_user_attachment"

  # group_name - (required) is a type of string
  group_name = null
  # user_name - (required) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required) - RBAC permission group name."
  type        = string
}

variable "user_name" {
  description = "(required) - Account user name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_rbac_group_user_attachment" "this" {
  group_name = var.group_name
  user_name  = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_rbac_group_user_attachment.this.id
}

output "this" {
  value = aviatrix_rbac_group_user_attachment.this
}
```

[top](#index)