# checkpoint_management_where_used

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_where_used" {
  source = "./modules/checkpoint/r/checkpoint_management_where_used"

  # dereference_group_members - (optional) is a type of bool
  dereference_group_members = null
  # indirect - (optional) is a type of bool
  indirect = null
  # indirect_max_depth - (optional) is a type of number
  indirect_max_depth = null
  # name - (required) is a type of string
  name = null
  # show_membership - (optional) is a type of bool
  show_membership = null
}
```

[top](#index)

### Variables

```terraform
variable "dereference_group_members" {
  description = "(optional) - Indicates whether to dereference \"members\" field by details level for every object in reply."
  type        = bool
  default     = null
}

variable "indirect" {
  description = "(optional) - Search for indirect usage."
  type        = bool
  default     = null
}

variable "indirect_max_depth" {
  description = "(optional) - Maximum nesting level during indirect usage search."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "show_membership" {
  description = "(optional) - Indicates whether to calculate and show \"groups\" field for every object in reply."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_where_used" "this" {
  dereference_group_members = var.dereference_group_members
  indirect                  = var.indirect
  indirect_max_depth        = var.indirect_max_depth
  name                      = var.name
  show_membership           = var.show_membership
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_where_used.this.id
}

output "this" {
  value = checkpoint_management_where_used.this
}
```

[top](#index)