# nsxt_policy_bgp_neighbor

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
module "nsxt_policy_bgp_neighbor" {
  source = "./modules/nsxt/r/nsxt_policy_bgp_neighbor"

  # allow_as_in - (optional) is a type of bool
  allow_as_in = null
  # bgp_path - (required) is a type of string
  bgp_path = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # graceful_restart_mode - (optional) is a type of string
  graceful_restart_mode = null
  # hold_down_time - (optional) is a type of number
  hold_down_time = null
  # keep_alive_time - (optional) is a type of number
  keep_alive_time = null
  # maximum_hop_limit - (optional) is a type of number
  maximum_hop_limit = null
  # neighbor_address - (required) is a type of string
  neighbor_address = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # password - (optional) is a type of string
  password = null
  # remote_as_num - (required) is a type of string
  remote_as_num = null
  # source_addresses - (optional) is a type of list of string
  source_addresses = []

  bfd_config = [{
    enabled  = null
    interval = null
    multiple = null
  }]

  route_filtering = [{
    address_family   = null
    enabled          = null
    in_route_filter  = null
    maximum_routes   = null
    out_route_filter = null
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
variable "allow_as_in" {
  description = "(optional) - Flag to enable allowas_in option for BGP neighbor"
  type        = bool
  default     = null
}

variable "bgp_path" {
  description = "(required) - Policy path to the BGP for this neighbor"
  type        = string
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "graceful_restart_mode" {
  description = "(optional) - BGP Graceful Restart Configuration Mode"
  type        = string
  default     = null
}

variable "hold_down_time" {
  description = "(optional) - Wait time in seconds before declaring peer dead"
  type        = number
  default     = null
}

variable "keep_alive_time" {
  description = "(optional) - Interval between keep alive messages sent to peer"
  type        = number
  default     = null
}

variable "maximum_hop_limit" {
  description = "(optional) - Maximum number of hops allowed to reach BGP neighbor"
  type        = number
  default     = null
}

variable "neighbor_address" {
  description = "(required) - Neighbor IP Address"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - Password for BGP neighbor authentication"
  type        = string
  default     = null
}

variable "remote_as_num" {
  description = "(required) - ASN of the neighbor in ASPLAIN or ASDOT Format"
  type        = string
}

variable "source_addresses" {
  description = "(optional) - Source IP Addresses for BGP peering"
  type        = list(string)
  default     = null
}

variable "bfd_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled  = bool
      interval = number
      multiple = number
    }
  ))
  default = []
}

variable "route_filtering" {
  description = "nested block: NestingList, min items: 0, max items: 2"
  type = set(object(
    {
      address_family   = string
      enabled          = bool
      in_route_filter  = string
      maximum_routes   = number
      out_route_filter = string
    }
  ))
  default = []
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
resource "nsxt_policy_bgp_neighbor" "this" {
  # allow_as_in - (optional) is a type of bool
  allow_as_in = var.allow_as_in
  # bgp_path - (required) is a type of string
  bgp_path = var.bgp_path
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # graceful_restart_mode - (optional) is a type of string
  graceful_restart_mode = var.graceful_restart_mode
  # hold_down_time - (optional) is a type of number
  hold_down_time = var.hold_down_time
  # keep_alive_time - (optional) is a type of number
  keep_alive_time = var.keep_alive_time
  # maximum_hop_limit - (optional) is a type of number
  maximum_hop_limit = var.maximum_hop_limit
  # neighbor_address - (required) is a type of string
  neighbor_address = var.neighbor_address
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # password - (optional) is a type of string
  password = var.password
  # remote_as_num - (required) is a type of string
  remote_as_num = var.remote_as_num
  # source_addresses - (optional) is a type of list of string
  source_addresses = var.source_addresses

  dynamic "bfd_config" {
    for_each = var.bfd_config
    content {
      # enabled - (optional) is a type of bool
      enabled = bfd_config.value["enabled"]
      # interval - (optional) is a type of number
      interval = bfd_config.value["interval"]
      # multiple - (optional) is a type of number
      multiple = bfd_config.value["multiple"]
    }
  }

  dynamic "route_filtering" {
    for_each = var.route_filtering
    content {
      # address_family - (required) is a type of string
      address_family = route_filtering.value["address_family"]
      # enabled - (optional) is a type of bool
      enabled = route_filtering.value["enabled"]
      # in_route_filter - (optional) is a type of string
      in_route_filter = route_filtering.value["in_route_filter"]
      # maximum_routes - (optional) is a type of number
      maximum_routes = route_filtering.value["maximum_routes"]
      # out_route_filter - (optional) is a type of string
      out_route_filter = route_filtering.value["out_route_filter"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_bgp_neighbor.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_bgp_neighbor.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_bgp_neighbor.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_bgp_neighbor.this.revision
}

output "this" {
  value = nsxt_policy_bgp_neighbor.this
}
```

[top](#index)