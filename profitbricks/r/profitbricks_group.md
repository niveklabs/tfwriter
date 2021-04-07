# profitbricks_group

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
module "profitbricks_group" {
  source = "./modules/profitbricks/r/profitbricks_group"

  # access_activity_log - (optional) is a type of bool
  access_activity_log = null
  # create_datacenter - (optional) is a type of bool
  create_datacenter = null
  # create_snapshot - (optional) is a type of bool
  create_snapshot = null
  # name - (required) is a type of string
  name = null
  # reserve_ip - (optional) is a type of bool
  reserve_ip = null
  # user_id - (optional) is a type of string
  user_id = null

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
variable "access_activity_log" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "create_datacenter" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "create_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "reserve_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "profitbricks_group" "this" {
  # access_activity_log - (optional) is a type of bool
  access_activity_log = var.access_activity_log
  # create_datacenter - (optional) is a type of bool
  create_datacenter = var.create_datacenter
  # create_snapshot - (optional) is a type of bool
  create_snapshot = var.create_snapshot
  # name - (required) is a type of string
  name = var.name
  # reserve_ip - (optional) is a type of bool
  reserve_ip = var.reserve_ip
  # user_id - (optional) is a type of string
  user_id = var.user_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_group.this.id
}

output "users" {
  description = "returns a set of object"
  value       = profitbricks_group.this.users
}

output "this" {
  value = profitbricks_group.this
}
```

[top](#index)