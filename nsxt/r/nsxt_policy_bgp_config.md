# nsxt_policy_bgp_config

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
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_bgp_config" {
  source = "./modules/nsxt/r/nsxt_policy_bgp_config"

  # ecmp - (optional) is a type of bool
  ecmp = null
  # enabled - (optional) is a type of bool
  enabled = null
  # gateway_path - (required) is a type of string
  gateway_path = null
  # graceful_restart_mode - (optional) is a type of string
  graceful_restart_mode = null
  # graceful_restart_stale_route_timer - (optional) is a type of number
  graceful_restart_stale_route_timer = null
  # graceful_restart_timer - (optional) is a type of number
  graceful_restart_timer = null
  # inter_sr_ibgp - (optional) is a type of bool
  inter_sr_ibgp = null
  # local_as_num - (optional) is a type of string
  local_as_num = null
  # multipath_relax - (optional) is a type of bool
  multipath_relax = null
  # site_path - (required) is a type of string
  site_path = null

  route_aggregation = [{
    prefix       = null
    summary_only = null
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
variable "ecmp" {
  description = "(optional) - Flag to enable ECMP"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - Flag to enable BGP configuration"
  type        = bool
  default     = null
}

variable "gateway_path" {
  description = "(required) - Gateway for this BGP config"
  type        = string
}

variable "graceful_restart_mode" {
  description = "(optional) - BGP Graceful Restart Configuration Mode"
  type        = string
  default     = null
}

variable "graceful_restart_stale_route_timer" {
  description = "(optional) - BGP Stale Route Timer"
  type        = number
  default     = null
}

variable "graceful_restart_timer" {
  description = "(optional) - BGP Graceful Restart Timer"
  type        = number
  default     = null
}

variable "inter_sr_ibgp" {
  description = "(optional) - Enable inter SR IBGP configuration"
  type        = bool
  default     = null
}

variable "local_as_num" {
  description = "(optional) - BGP AS number in ASPLAIN/ASDOT Format"
  type        = string
  default     = null
}

variable "multipath_relax" {
  description = "(optional) - Flag to enable BGP multipath relax option"
  type        = bool
  default     = null
}

variable "site_path" {
  description = "(required) - Site Path for this BGP config"
  type        = string
}

variable "route_aggregation" {
  description = "nested block: NestingList, min items: 0, max items: 1000"
  type = set(object(
    {
      prefix       = string
      summary_only = bool
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
resource "nsxt_policy_bgp_config" "this" {
  ecmp                               = var.ecmp
  enabled                            = var.enabled
  gateway_path                       = var.gateway_path
  graceful_restart_mode              = var.graceful_restart_mode
  graceful_restart_stale_route_timer = var.graceful_restart_stale_route_timer
  graceful_restart_timer             = var.graceful_restart_timer
  inter_sr_ibgp                      = var.inter_sr_ibgp
  local_as_num                       = var.local_as_num
  multipath_relax                    = var.multipath_relax
  site_path                          = var.site_path

  dynamic "route_aggregation" {
    for_each = var.route_aggregation
    content {
      prefix       = route_aggregation.value["prefix"]
      summary_only = route_aggregation.value["summary_only"]
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
output "id" {
  description = "returns a string"
  value       = nsxt_policy_bgp_config.this.id
}

output "inter_sr_ibgp" {
  description = "returns a bool"
  value       = nsxt_policy_bgp_config.this.inter_sr_ibgp
}

output "multipath_relax" {
  description = "returns a bool"
  value       = nsxt_policy_bgp_config.this.multipath_relax
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_bgp_config.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_bgp_config.this.revision
}

output "this" {
  value = nsxt_policy_bgp_config.this
}
```

[top](#index)