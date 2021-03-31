# aviatrix_rbac_group_access_account_attachment

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
module "aviatrix_rbac_group_access_account_attachment" {
  source = "./modules/aviatrix/r/aviatrix_rbac_group_access_account_attachment"

  # access_account_name - (required) is a type of string
  access_account_name = null
  # group_name - (required) is a type of string
  group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "access_account_name" {
  description = "(required) - Access account name."
  type        = string
}

variable "group_name" {
  description = "(required) - RBAC permission group name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_rbac_group_access_account_attachment" "this" {
  access_account_name = var.access_account_name
  group_name          = var.group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_rbac_group_access_account_attachment.this.id
}

output "this" {
  value = aviatrix_rbac_group_access_account_attachment.this
}
```

[top](#index)