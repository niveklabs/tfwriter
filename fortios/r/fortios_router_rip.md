# fortios_router_rip

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
module "fortios_router_rip" {
  source = "./modules/fortios/r/fortios_router_rip"

  # default_information_originate - (optional) is a type of string
  default_information_originate = null
  # default_metric - (optional) is a type of number
  default_metric = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # garbage_timer - (optional) is a type of number
  garbage_timer = null
  # max_out_metric - (optional) is a type of number
  max_out_metric = null
  # recv_buffer_size - (optional) is a type of number
  recv_buffer_size = null
  # timeout_timer - (optional) is a type of number
  timeout_timer = null
  # update_timer - (optional) is a type of number
  update_timer = null
  # version - (optional) is a type of string
  version = null

  distance = [{
    access_list = null
    distance    = null
    id          = null
    prefix      = null
  }]

  distribute_list = [{
    direction = null
    id        = null
    interface = null
    listname  = null
    status    = null
  }]

  interface = [{
    auth_keychain           = null
    auth_mode               = null
    auth_string             = null
    flags                   = null
    name                    = null
    receive_version         = null
    send_version            = null
    send_version2_broadcast = null
    split_horizon           = null
    split_horizon_status    = null
  }]

  neighbor = [{
    id = null
    ip = null
  }]

  network = [{
    id     = null
    prefix = null
  }]

  offset_list = [{
    access_list = null
    direction   = null
    id          = null
    interface   = null
    offset      = null
    status      = null
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

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
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

variable "recv_buffer_size" {
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

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distance" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_list = string
      distance    = number
      id          = number
      prefix      = string
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
      auth_keychain           = string
      auth_mode               = string
      auth_string             = string
      flags                   = number
      name                    = string
      receive_version         = string
      send_version            = string
      send_version2_broadcast = string
      split_horizon           = string
      split_horizon_status    = string
    }
  ))
  default = []
}

variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
      ip = string
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
      access_list = string
      direction   = string
      id          = number
      interface   = string
      offset      = number
      status      = string
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
resource "fortios_router_rip" "this" {
  default_information_originate = var.default_information_originate
  default_metric                = var.default_metric
  dynamic_sort_subtable         = var.dynamic_sort_subtable
  garbage_timer                 = var.garbage_timer
  max_out_metric                = var.max_out_metric
  recv_buffer_size              = var.recv_buffer_size
  timeout_timer                 = var.timeout_timer
  update_timer                  = var.update_timer
  version                       = var.version

  dynamic "distance" {
    for_each = var.distance
    content {
      access_list = distance.value["access_list"]
      distance    = distance.value["distance"]
      id          = distance.value["id"]
      prefix      = distance.value["prefix"]
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
      auth_keychain           = interface.value["auth_keychain"]
      auth_mode               = interface.value["auth_mode"]
      auth_string             = interface.value["auth_string"]
      flags                   = interface.value["flags"]
      name                    = interface.value["name"]
      receive_version         = interface.value["receive_version"]
      send_version            = interface.value["send_version"]
      send_version2_broadcast = interface.value["send_version2_broadcast"]
      split_horizon           = interface.value["split_horizon"]
      split_horizon_status    = interface.value["split_horizon_status"]
    }
  }

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      id = neighbor.value["id"]
      ip = neighbor.value["ip"]
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
      access_list = offset_list.value["access_list"]
      direction   = offset_list.value["direction"]
      id          = offset_list.value["id"]
      interface   = offset_list.value["interface"]
      offset      = offset_list.value["offset"]
      status      = offset_list.value["status"]
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
  value       = fortios_router_rip.this.default_information_originate
}

output "default_metric" {
  description = "returns a number"
  value       = fortios_router_rip.this.default_metric
}

output "garbage_timer" {
  description = "returns a number"
  value       = fortios_router_rip.this.garbage_timer
}

output "id" {
  description = "returns a string"
  value       = fortios_router_rip.this.id
}

output "max_out_metric" {
  description = "returns a number"
  value       = fortios_router_rip.this.max_out_metric
}

output "recv_buffer_size" {
  description = "returns a number"
  value       = fortios_router_rip.this.recv_buffer_size
}

output "timeout_timer" {
  description = "returns a number"
  value       = fortios_router_rip.this.timeout_timer
}

output "update_timer" {
  description = "returns a number"
  value       = fortios_router_rip.this.update_timer
}

output "version" {
  description = "returns a string"
  value       = fortios_router_rip.this.version
}

output "this" {
  value = fortios_router_rip.this
}
```

[top](#index)