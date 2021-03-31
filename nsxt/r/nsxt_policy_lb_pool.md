# nsxt_policy_lb_pool

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
module "nsxt_policy_lb_pool" {
  source = "./modules/nsxt/r/nsxt_policy_lb_pool"

  # active_monitor_path - (optional) is a type of string
  active_monitor_path = null
  # algorithm - (optional) is a type of string
  algorithm = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # min_active_members - (optional) is a type of number
  min_active_members = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # passive_monitor_path - (optional) is a type of string
  passive_monitor_path = null
  # tcp_multiplexing_enabled - (optional) is a type of bool
  tcp_multiplexing_enabled = null
  # tcp_multiplexing_number - (optional) is a type of number
  tcp_multiplexing_number = null

  member = [{
    admin_state                = null
    backup_member              = null
    display_name               = null
    ip_address                 = null
    max_concurrent_connections = null
    port                       = null
    weight                     = null
  }]

  member_group = [{
    allow_ipv4       = null
    allow_ipv6       = null
    group_path       = null
    max_ip_list_size = null
    port             = null
  }]

  snat = [{
    ip_pool_addresses = []
    type              = null
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
variable "active_monitor_path" {
  description = "(optional) - Active healthcheck is disabled by default and can be enabled using this setting"
  type        = string
  default     = null
}

variable "algorithm" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "min_active_members" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "passive_monitor_path" {
  description = "(optional) - Policy path for passive health monitor"
  type        = string
  default     = null
}

variable "tcp_multiplexing_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tcp_multiplexing_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      admin_state                = string
      backup_member              = bool
      display_name               = string
      ip_address                 = string
      max_concurrent_connections = number
      port                       = string
      weight                     = number
    }
  ))
  default = []
}

variable "member_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_ipv4       = bool
      allow_ipv6       = bool
      group_path       = string
      max_ip_list_size = number
      port             = string
    }
  ))
  default = []
}

variable "snat" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_pool_addresses = list(string)
      type              = string
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
resource "nsxt_policy_lb_pool" "this" {
  active_monitor_path      = var.active_monitor_path
  algorithm                = var.algorithm
  description              = var.description
  display_name             = var.display_name
  min_active_members       = var.min_active_members
  nsx_id                   = var.nsx_id
  passive_monitor_path     = var.passive_monitor_path
  tcp_multiplexing_enabled = var.tcp_multiplexing_enabled
  tcp_multiplexing_number  = var.tcp_multiplexing_number

  dynamic "member" {
    for_each = var.member
    content {
      admin_state                = member.value["admin_state"]
      backup_member              = member.value["backup_member"]
      display_name               = member.value["display_name"]
      ip_address                 = member.value["ip_address"]
      max_concurrent_connections = member.value["max_concurrent_connections"]
      port                       = member.value["port"]
      weight                     = member.value["weight"]
    }
  }

  dynamic "member_group" {
    for_each = var.member_group
    content {
      allow_ipv4       = member_group.value["allow_ipv4"]
      allow_ipv6       = member_group.value["allow_ipv6"]
      group_path       = member_group.value["group_path"]
      max_ip_list_size = member_group.value["max_ip_list_size"]
      port             = member_group.value["port"]
    }
  }

  dynamic "snat" {
    for_each = var.snat
    content {
      ip_pool_addresses = snat.value["ip_pool_addresses"]
      type              = snat.value["type"]
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
  value       = nsxt_policy_lb_pool.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_lb_pool.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_lb_pool.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_lb_pool.this.revision
}

output "this" {
  value = nsxt_policy_lb_pool.this
}
```

[top](#index)