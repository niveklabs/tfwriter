# fortios_wirelesscontroller_intercontroller

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontroller_intercontroller" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_intercontroller"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fast_failover_max - (optional) is a type of number
  fast_failover_max = null
  # fast_failover_wait - (optional) is a type of number
  fast_failover_wait = null
  # inter_controller_key - (optional) is a type of string
  inter_controller_key = null
  # inter_controller_mode - (optional) is a type of string
  inter_controller_mode = null
  # inter_controller_pri - (optional) is a type of string
  inter_controller_pri = null

  inter_controller_peer = [{
    id            = null
    peer_ip       = null
    peer_port     = null
    peer_priority = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fast_failover_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fast_failover_wait" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "inter_controller_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inter_controller_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inter_controller_pri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inter_controller_peer" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id            = number
      peer_ip       = string
      peer_port     = number
      peer_priority = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_intercontroller" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fast_failover_max - (optional) is a type of number
  fast_failover_max = var.fast_failover_max
  # fast_failover_wait - (optional) is a type of number
  fast_failover_wait = var.fast_failover_wait
  # inter_controller_key - (optional) is a type of string
  inter_controller_key = var.inter_controller_key
  # inter_controller_mode - (optional) is a type of string
  inter_controller_mode = var.inter_controller_mode
  # inter_controller_pri - (optional) is a type of string
  inter_controller_pri = var.inter_controller_pri

  dynamic "inter_controller_peer" {
    for_each = var.inter_controller_peer
    content {
      # id - (optional) is a type of number
      id = inter_controller_peer.value["id"]
      # peer_ip - (optional) is a type of string
      peer_ip = inter_controller_peer.value["peer_ip"]
      # peer_port - (optional) is a type of number
      peer_port = inter_controller_peer.value["peer_port"]
      # peer_priority - (optional) is a type of string
      peer_priority = inter_controller_peer.value["peer_priority"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fast_failover_max" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_intercontroller.this.fast_failover_max
}

output "fast_failover_wait" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_intercontroller.this.fast_failover_wait
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_intercontroller.this.id
}

output "inter_controller_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_intercontroller.this.inter_controller_mode
}

output "inter_controller_pri" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_intercontroller.this.inter_controller_pri
}

output "this" {
  value = fortios_wirelesscontroller_intercontroller.this
}
```

[top](#index)