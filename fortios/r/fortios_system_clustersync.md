# fortios_system_clustersync

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
module "fortios_system_clustersync" {
  source = "./modules/fortios/r/fortios_system_clustersync"

  # hb_interval - (optional) is a type of number
  hb_interval = null
  # hb_lost_threshold - (optional) is a type of number
  hb_lost_threshold = null
  # peerip - (optional) is a type of string
  peerip = null
  # peervd - (optional) is a type of string
  peervd = null
  # slave_add_ike_routes - (optional) is a type of string
  slave_add_ike_routes = null
  # sync_id - (optional) is a type of number
  sync_id = null

  down_intfs_before_sess_sync = [{
    name = null
  }]

  session_sync_filter = [{
    custom_service = [{
      dst_port_range = null
      id             = null
      src_port_range = null
    }]
    dstaddr  = null
    dstaddr6 = null
    dstintf  = null
    srcaddr  = null
    srcaddr6 = null
    srcintf  = null
  }]

  syncvd = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "hb_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hb_lost_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "peerip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peervd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "slave_add_ike_routes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sync_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "down_intfs_before_sess_sync" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "session_sync_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      custom_service = list(object(
        {
          dst_port_range = string
          id             = number
          src_port_range = string
        }
      ))
      dstaddr  = string
      dstaddr6 = string
      dstintf  = string
      srcaddr  = string
      srcaddr6 = string
      srcintf  = string
    }
  ))
  default = []
}

variable "syncvd" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_clustersync" "this" {
  hb_interval          = var.hb_interval
  hb_lost_threshold    = var.hb_lost_threshold
  peerip               = var.peerip
  peervd               = var.peervd
  slave_add_ike_routes = var.slave_add_ike_routes
  sync_id              = var.sync_id

  dynamic "down_intfs_before_sess_sync" {
    for_each = var.down_intfs_before_sess_sync
    content {
      name = down_intfs_before_sess_sync.value["name"]
    }
  }

  dynamic "session_sync_filter" {
    for_each = var.session_sync_filter
    content {
      dstaddr  = session_sync_filter.value["dstaddr"]
      dstaddr6 = session_sync_filter.value["dstaddr6"]
      dstintf  = session_sync_filter.value["dstintf"]
      srcaddr  = session_sync_filter.value["srcaddr"]
      srcaddr6 = session_sync_filter.value["srcaddr6"]
      srcintf  = session_sync_filter.value["srcintf"]

      dynamic "custom_service" {
        for_each = session_sync_filter.value.custom_service
        content {
          dst_port_range = custom_service.value["dst_port_range"]
          id             = custom_service.value["id"]
          src_port_range = custom_service.value["src_port_range"]
        }
      }

    }
  }

  dynamic "syncvd" {
    for_each = var.syncvd
    content {
      name = syncvd.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "hb_interval" {
  description = "returns a number"
  value       = fortios_system_clustersync.this.hb_interval
}

output "hb_lost_threshold" {
  description = "returns a number"
  value       = fortios_system_clustersync.this.hb_lost_threshold
}

output "id" {
  description = "returns a string"
  value       = fortios_system_clustersync.this.id
}

output "peerip" {
  description = "returns a string"
  value       = fortios_system_clustersync.this.peerip
}

output "peervd" {
  description = "returns a string"
  value       = fortios_system_clustersync.this.peervd
}

output "slave_add_ike_routes" {
  description = "returns a string"
  value       = fortios_system_clustersync.this.slave_add_ike_routes
}

output "sync_id" {
  description = "returns a number"
  value       = fortios_system_clustersync.this.sync_id
}

output "this" {
  value = fortios_system_clustersync.this
}
```

[top](#index)