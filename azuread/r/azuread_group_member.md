# azuread_group_member

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_group_member" {
  source = "./modules/azuread/r/azuread_group_member"

  # group_object_id - (required) is a type of string
  group_object_id = null
  # member_object_id - (required) is a type of string
  member_object_id = null
}
```

[top](#index)

### Variables

```terraform
variable "group_object_id" {
  description = "(required)"
  type        = string
}

variable "member_object_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuread_group_member" "this" {
  # group_object_id - (required) is a type of string
  group_object_id = var.group_object_id
  # member_object_id - (required) is a type of string
  member_object_id = var.member_object_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuread_group_member.this.id
}

output "this" {
  value = azuread_group_member.this
}
```

[top](#index)