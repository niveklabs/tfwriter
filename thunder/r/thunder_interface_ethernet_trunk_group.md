# thunder_interface_ethernet_trunk_group

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_interface_ethernet_trunk_group" {
  source = "./modules/thunder/r/thunder_interface_ethernet_trunk_group"

  # admin_key - (optional) is a type of number
  admin_key = null
  # ifnum - (optional) is a type of number
  ifnum = null
  # mode - (optional) is a type of string
  mode = null
  # port_priority - (optional) is a type of number
  port_priority = null
  # timeout - (optional) is a type of string
  timeout = null
  # trunk_number - (optional) is a type of number
  trunk_number = null
  # type - (optional) is a type of string
  type = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  udld_timeout_cfg = [{
    fast = null
    slow = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_key" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ifnum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trunk_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "udld_timeout_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fast = number
      slow = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_interface_ethernet_trunk_group" "this" {
  admin_key     = var.admin_key
  ifnum         = var.ifnum
  mode          = var.mode
  port_priority = var.port_priority
  timeout       = var.timeout
  trunk_number  = var.trunk_number
  type          = var.type
  user_tag      = var.user_tag
  uuid          = var.uuid

  dynamic "udld_timeout_cfg" {
    for_each = var.udld_timeout_cfg
    content {
      fast = udld_timeout_cfg.value["fast"]
      slow = udld_timeout_cfg.value["slow"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_ethernet_trunk_group.this.id
}

output "this" {
  value = thunder_interface_ethernet_trunk_group.this
}
```

[top](#index)