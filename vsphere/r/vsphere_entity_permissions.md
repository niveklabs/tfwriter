# vsphere_entity_permissions

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_entity_permissions" {
  source = "./modules/vsphere/r/vsphere_entity_permissions"

  # entity_id - (required) is a type of string
  entity_id = null
  # entity_type - (required) is a type of string
  entity_type = null

  permissions = [{
    is_group      = null
    propagate     = null
    role_id       = null
    user_or_group = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "entity_id" {
  description = "(required) - The managed object id or uuid of the entity."
  type        = string
}

variable "entity_type" {
  description = "(required) - The entity managed object type."
  type        = string
}

variable "permissions" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      is_group      = bool
      propagate     = bool
      role_id       = string
      user_or_group = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_entity_permissions" "this" {
  entity_id   = var.entity_id
  entity_type = var.entity_type

  dynamic "permissions" {
    for_each = var.permissions
    content {
      is_group      = permissions.value["is_group"]
      propagate     = permissions.value["propagate"]
      role_id       = permissions.value["role_id"]
      user_or_group = permissions.value["user_or_group"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_entity_permissions.this.id
}

output "this" {
  value = vsphere_entity_permissions.this
}
```

[top](#index)