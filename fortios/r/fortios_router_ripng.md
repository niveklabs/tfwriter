# fortios_router_ripng

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_router_ripng" {
  source = "./modules/fortios/r/fortios_router_ripng"

  # default_information_originate - (optional) is a type of string
  default_information_originate = null
  # default_metric - (optional) is a type of number
  default_metric = null
  # garbage_timer - (optional) is a type of number
  garbage_timer = null
  # max_out_metric - (optional) is a type of number
  max_out_metric = null
  # timeout_timer - (optional) is a type of number
  timeout_timer = null
  # update_timer - (optional) is a type of number
  update_timer = null

  aggregate_address = [{
    id      = null
    prefix6 = null
  }]

  distance = [{
    access_list6 = null
    distance     = null
    id           = null
    prefix6      = null
  }]

  distribute_list = [{
    direction = null
    id        = null
    interface = null
    listname  = null
    status    = null
  }]

  interface = [{
    flags                = null
    name                 = null
    split_horizon        = null
    split_horizon_status = null
  }]

  neighbor = [{
    id        = null
    interface = null
    ip6       = null
  }]

  network = [{
    id     = null
    prefix = null
  }]

  offset_list = [{
    access_list6 = null
    direction    = null
    id           = null
    interface    = null
    offset       = null
    status       = null
  }]

  passive_interface = [{
    name = null
  }]

  redistribute = [{
    metric   = null
    name     = null
    routemap = null
    status   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_information_originate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "garbage_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_out_metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "update_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "aggregate_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id      = number
      prefix6 = string
    }
  ))
  default = []
}

variable "distance" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_list6 = string
      distance     = number
      id           = number
      prefix6      = string
    }
  ))
  default = []
}

variable "distribute_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      direction = string
      id        = number
      interface = string
      listname  = string
      status    = string
    }
  ))
  default = []
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      flags                = number
      name                 = string
      split_horizon        = string
      split_horizon_status = string
    }
  ))
  default = []
}

variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id        = number
      interface = string
      ip6       = string
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id     = number
      prefix = string
    }
  ))
  default = []
}

variable "offset_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_list6 = string
      direction    = string
      id           = number
      interface    = string
      offset       = number
      status       = string
    }
  ))
  default = []
}

variable "passive_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "redistribute" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      metric   = number
      name     = string
      routemap = string
      status   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_ripng" "this" {
  default_information_originate = var.default_information_originate
  default_metric                = var.default_metric
  garbage_timer                 = var.garbage_timer
  max_out_metric                = var.max_out_metric
  timeout_timer                 = var.timeout_timer
  update_timer                  = var.update_timer

  dynamic "aggregate_address" {
    for_each = var.aggregate_address
    content {
      id      = aggregate_address.value["id"]
      prefix6 = aggregate_address.value["prefix6"]
    }
  }

  dynamic "distance" {
    for_each = var.distance
    content {
      access_list6 = distance.value["access_list6"]
      distance     = distance.value["distance"]
      id           = distance.value["id"]
      prefix6      = distance.value["prefix6"]
    }
  }

  dynamic "distribute_list" {
    for_each = var.distribute_list
    content {
      direction = distribute_list.value["direction"]
      id        = distribute_list.value["id"]
      interface = distribute_list.value["interface"]
      listname  = distribute_list.value["listname"]
      status    = distribute_list.value["status"]
    }
  }

  dynamic "interface" {
    for_each = var.interface
    content {
      flags                = interface.value["flags"]
      name                 = interface.value["name"]
      split_horizon        = interface.value["split_horizon"]
      split_horizon_status = interface.value["split_horizon_status"]
    }
  }

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      id        = neighbor.value["id"]
      interface = neighbor.value["interface"]
      ip6       = neighbor.value["ip6"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      id     = network.value["id"]
      prefix = network.value["prefix"]
    }
  }

  dynamic "offset_list" {
    for_each = var.offset_list
    content {
      access_list6 = offset_list.value["access_list6"]
      direction    = offset_list.value["direction"]
      id           = offset_list.value["id"]
      interface    = offset_list.value["interface"]
      offset       = offset_list.value["offset"]
      status       = offset_list.value["status"]
    }
  }

  dynamic "passive_interface" {
    for_each = var.passive_interface
    content {
      name = passive_interface.value["name"]
    }
  }

  dynamic "redistribute" {
    for_each = var.redistribute
    content {
      metric   = redistribute.value["metric"]
      name     = redistribute.value["name"]
      routemap = redistribute.value["routemap"]
      status   = redistribute.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_information_originate" {
  description = "returns a string"
  value       = fortios_router_ripng.this.default_information_originate
}

output "default_metric" {
  description = "returns a number"
  value       = fortios_router_ripng.this.default_metric
}

output "garbage_timer" {
  description = "returns a number"
  value       = fortios_router_ripng.this.garbage_timer
}

output "id" {
  description = "returns a string"
  value       = fortios_router_ripng.this.id
}

output "max_out_metric" {
  description = "returns a number"
  value       = fortios_router_ripng.this.max_out_metric
}

output "timeout_timer" {
  description = "returns a number"
  value       = fortios_router_ripng.this.timeout_timer
}

output "update_timer" {
  description = "returns a number"
  value       = fortios_router_ripng.this.update_timer
}

output "this" {
  value = fortios_router_ripng.this
}
```

[top](#index)