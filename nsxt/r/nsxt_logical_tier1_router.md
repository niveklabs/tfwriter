# nsxt_logical_tier1_router

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
module "nsxt_logical_tier1_router" {
  source = "./modules/nsxt/r/nsxt_logical_tier1_router"

  # advertise_connected_routes - (optional) is a type of bool
  advertise_connected_routes = null
  # advertise_lb_snat_ip_routes - (optional) is a type of bool
  advertise_lb_snat_ip_routes = null
  # advertise_lb_vip_routes - (optional) is a type of bool
  advertise_lb_vip_routes = null
  # advertise_nat_routes - (optional) is a type of bool
  advertise_nat_routes = null
  # advertise_static_routes - (optional) is a type of bool
  advertise_static_routes = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = null
  # enable_router_advertisement - (optional) is a type of bool
  enable_router_advertisement = null
  # failover_mode - (optional) is a type of string
  failover_mode = null

  firewall_sections = [{
    is_valid            = null
    target_display_name = null
    target_id           = null
    target_type         = null
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
variable "advertise_connected_routes" {
  description = "(optional) - Enable connected NSX routes advertisement"
  type        = bool
  default     = null
}

variable "advertise_lb_snat_ip_routes" {
  description = "(optional) - Enable LB SNAT IP routes advertisement"
  type        = bool
  default     = null
}

variable "advertise_lb_vip_routes" {
  description = "(optional) - Enable LB VIP routes advertisement"
  type        = bool
  default     = null
}

variable "advertise_nat_routes" {
  description = "(optional) - Enable NAT routes advertisement"
  type        = bool
  default     = null
}

variable "advertise_static_routes" {
  description = "(optional) - Enable static routes advertisement"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "edge_cluster_id" {
  description = "(optional) - Edge Cluster Id"
  type        = string
  default     = null
}

variable "enable_router_advertisement" {
  description = "(optional) - Enable router advertisement"
  type        = bool
  default     = null
}

variable "failover_mode" {
  description = "(optional) - Failover mode which determines whether the preferred service router instance for given logical router will preempt the peer"
  type        = string
  default     = null
}

variable "firewall_sections" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_valid            = bool
      target_display_name = string
      target_id           = string
      target_type         = string
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
resource "nsxt_logical_tier1_router" "this" {
  # advertise_connected_routes - (optional) is a type of bool
  advertise_connected_routes = var.advertise_connected_routes
  # advertise_lb_snat_ip_routes - (optional) is a type of bool
  advertise_lb_snat_ip_routes = var.advertise_lb_snat_ip_routes
  # advertise_lb_vip_routes - (optional) is a type of bool
  advertise_lb_vip_routes = var.advertise_lb_vip_routes
  # advertise_nat_routes - (optional) is a type of bool
  advertise_nat_routes = var.advertise_nat_routes
  # advertise_static_routes - (optional) is a type of bool
  advertise_static_routes = var.advertise_static_routes
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = var.edge_cluster_id
  # enable_router_advertisement - (optional) is a type of bool
  enable_router_advertisement = var.enable_router_advertisement
  # failover_mode - (optional) is a type of string
  failover_mode = var.failover_mode

  dynamic "firewall_sections" {
    for_each = var.firewall_sections
    content {
      # target_id - (optional) is a type of string
      target_id = firewall_sections.value["target_id"]
      # target_type - (optional) is a type of string
      target_type = firewall_sections.value["target_type"]
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
output "advertise_config_revision" {
  description = "returns a number"
  value       = nsxt_logical_tier1_router.this.advertise_config_revision
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_logical_tier1_router.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_logical_tier1_router.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_logical_tier1_router.this.revision
}

output "this" {
  value = nsxt_logical_tier1_router.this
}
```

[top](#index)