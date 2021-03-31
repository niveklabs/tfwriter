# nsxt_static_route

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_static_route" {
  source = "./modules/nsxt/r/nsxt_static_route"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # logical_router_id - (required) is a type of string
  logical_router_id = null
  # network - (required) is a type of string
  network = null

  next_hop = [{
    administrative_distance = null
    bfd_enabled             = null
    blackhole_action        = null
    ip_address              = null
    logical_router_port_id  = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Defaults to ID if not set"
  type        = string
  default     = null
}

variable "logical_router_id" {
  description = "(required) - Logical router id"
  type        = string
}

variable "network" {
  description = "(required) - CIDR"
  type        = string
}

variable "next_hop" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      administrative_distance = number
      bfd_enabled             = bool
      blackhole_action        = string
      ip_address              = string
      logical_router_port_id  = string
    }
  ))
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_static_route" "this" {
  description       = var.description
  display_name      = var.display_name
  logical_router_id = var.logical_router_id
  network           = var.network

  dynamic "next_hop" {
    for_each = var.next_hop
    content {
      administrative_distance = next_hop.value["administrative_distance"]
      ip_address              = next_hop.value["ip_address"]
      logical_router_port_id  = next_hop.value["logical_router_port_id"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_static_route.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_static_route.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_static_route.this.revision
}

output "this" {
  value = nsxt_static_route.this
}
```

[top](#index)