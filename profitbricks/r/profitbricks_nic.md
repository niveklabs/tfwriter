# profitbricks_nic

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
module "profitbricks_nic" {
  source = "./modules/profitbricks/r/profitbricks_nic"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # dhcp - (optional) is a type of bool
  dhcp = null
  # firewall_active - (optional) is a type of bool
  firewall_active = null
  # ip - (optional) is a type of string
  ip = null
  # lan - (required) is a type of number
  lan = null
  # name - (optional) is a type of string
  name = null
  # nat - (optional) is a type of bool
  nat = null
  # server_id - (required) is a type of string
  server_id = null

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
variable "datacenter_id" {
  description = "(required)"
  type        = string
}

variable "dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "firewall_active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lan" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = string
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
resource "profitbricks_nic" "this" {
  datacenter_id   = var.datacenter_id
  dhcp            = var.dhcp
  firewall_active = var.firewall_active
  ip              = var.ip
  lan             = var.lan
  name            = var.name
  nat             = var.nat
  server_id       = var.server_id

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
  value       = profitbricks_nic.this.id
}

output "ips" {
  description = "returns a list of string"
  value       = profitbricks_nic.this.ips
}

output "mac" {
  description = "returns a string"
  value       = profitbricks_nic.this.mac
}

output "this" {
  value = profitbricks_nic.this
}
```

[top](#index)