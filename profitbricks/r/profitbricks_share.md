# profitbricks_share

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_share" {
  source = "./modules/profitbricks/r/profitbricks_share"

  # edit_privilege - (required) is a type of bool
  edit_privilege = null
  # group_id - (required) is a type of string
  group_id = null
  # resource_id - (required) is a type of string
  resource_id = null
  # share_privilege - (required) is a type of bool
  share_privilege = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "edit_privilege" {
  description = "(required)"
  type        = bool
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "share_privilege" {
  description = "(required)"
  type        = bool
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_share" "this" {
  edit_privilege  = var.edit_privilege
  group_id        = var.group_id
  resource_id     = var.resource_id
  share_privilege = var.share_privilege

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_share.this.id
}

output "this" {
  value = profitbricks_share.this
}
```

[top](#index)