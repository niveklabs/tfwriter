# nsxt_lb_pool

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
module "nsxt_lb_pool" {
  source = "./modules/nsxt/r/nsxt_lb_pool"

  # active_monitor_id - (optional) is a type of string
  active_monitor_id = null
  # algorithm - (optional) is a type of string
  algorithm = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # min_active_members - (optional) is a type of number
  min_active_members = null
  # passive_monitor_id - (optional) is a type of string
  passive_monitor_id = null
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
    grouping_object = [{
      is_valid            = null
      target_display_name = null
      target_id           = null
      target_type         = null
    }]
    ip_version_filter  = null
    limit_ip_list_size = null
    max_ip_list_size   = null
    port               = null
  }]

  snat_translation = [{
    ip   = null
    type = null
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
variable "active_monitor_id" {
  description = "(optional) - Active health monitor Id. If one is not set, the active healthchecks will be disabled"
  type        = string
  default     = null
}

variable "algorithm" {
  description = "(optional) - Load balancing algorithm controls how the incoming connections are distributed among the members"
  type        = string
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

variable "min_active_members" {
  description = "(optional) - The minimum number of members for the pool to be considered active"
  type        = number
  default     = null
}

variable "passive_monitor_id" {
  description = "(optional) - Passive health monitor Id. If one is not set, the passive healthchecks will be disabled"
  type        = string
  default     = null
}

variable "tcp_multiplexing_enabled" {
  description = "(optional) - TCP multiplexing allows the same TCP connection between load balancer and the backend server to be used for sending multiple client requests from different client TCP connections"
  type        = bool
  default     = null
}

variable "tcp_multiplexing_number" {
  description = "(optional) - The maximum number of TCP connections per pool that are idly kept alive for sending future client requests"
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
      grouping_object = list(object(
        {
          is_valid            = bool
          target_display_name = string
          target_id           = string
          target_type         = string
        }
      ))
      ip_version_filter  = string
      limit_ip_list_size = bool
      max_ip_list_size   = number
      port               = number
    }
  ))
  default = []
}

variable "snat_translation" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip   = string
      type = string
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
resource "nsxt_lb_pool" "this" {
  active_monitor_id        = var.active_monitor_id
  algorithm                = var.algorithm
  description              = var.description
  display_name             = var.display_name
  min_active_members       = var.min_active_members
  passive_monitor_id       = var.passive_monitor_id
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
      ip_version_filter  = member_group.value["ip_version_filter"]
      limit_ip_list_size = member_group.value["limit_ip_list_size"]
      max_ip_list_size   = member_group.value["max_ip_list_size"]
      port               = member_group.value["port"]

      dynamic "grouping_object" {
        for_each = member_group.value.grouping_object
        content {
          target_id   = grouping_object.value["target_id"]
          target_type = grouping_object.value["target_type"]
        }
      }

    }
  }

  dynamic "snat_translation" {
    for_each = var.snat_translation
    content {
      ip   = snat_translation.value["ip"]
      type = snat_translation.value["type"]
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
  value       = nsxt_lb_pool.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_pool.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_pool.this.revision
}

output "this" {
  value = nsxt_lb_pool.this
}
```

[top](#index)