# thunder_vrrp_common

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_vrrp_common" {
  source = "./modules/thunder/r/thunder_vrrp_common"

  # action - (optional) is a type of string
  action = null
  # arp_retry - (optional) is a type of number
  arp_retry = null
  # dead_timer - (optional) is a type of number
  dead_timer = null
  # device_id - (optional) is a type of number
  device_id = null
  # disable_default_vrid - (optional) is a type of number
  disable_default_vrid = null
  # forward_l4_packet_on_standby - (optional) is a type of number
  forward_l4_packet_on_standby = null
  # get_ready_time - (optional) is a type of number
  get_ready_time = null
  # hello_interval - (optional) is a type of number
  hello_interval = null
  # preemption_delay - (optional) is a type of number
  preemption_delay = null
  # restart_time - (optional) is a type of number
  restart_time = null
  # set_id - (optional) is a type of number
  set_id = null
  # track_event_delay - (optional) is a type of number
  track_event_delay = null
  # uuid - (optional) is a type of string
  uuid = null

  hostid_append_to_vrid = [{
    hostid_append_to_vrid_default = null
    hostid_append_to_vrid_value   = null
  }]

  inline_mode_cfg = [{
    inline_mode     = null
    preferred_port  = null
    preferred_trunk = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dead_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_default_vrid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_l4_packet_on_standby" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "get_ready_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hello_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preemption_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "restart_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "set_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "track_event_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostid_append_to_vrid" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      hostid_append_to_vrid_default = number
      hostid_append_to_vrid_value   = number
    }
  ))
  default = []
}

variable "inline_mode_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inline_mode     = number
      preferred_port  = number
      preferred_trunk = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_vrrp_common" "this" {
  action                       = var.action
  arp_retry                    = var.arp_retry
  dead_timer                   = var.dead_timer
  device_id                    = var.device_id
  disable_default_vrid         = var.disable_default_vrid
  forward_l4_packet_on_standby = var.forward_l4_packet_on_standby
  get_ready_time               = var.get_ready_time
  hello_interval               = var.hello_interval
  preemption_delay             = var.preemption_delay
  restart_time                 = var.restart_time
  set_id                       = var.set_id
  track_event_delay            = var.track_event_delay
  uuid                         = var.uuid

  dynamic "hostid_append_to_vrid" {
    for_each = var.hostid_append_to_vrid
    content {
      hostid_append_to_vrid_default = hostid_append_to_vrid.value["hostid_append_to_vrid_default"]
      hostid_append_to_vrid_value   = hostid_append_to_vrid.value["hostid_append_to_vrid_value"]
    }
  }

  dynamic "inline_mode_cfg" {
    for_each = var.inline_mode_cfg
    content {
      inline_mode     = inline_mode_cfg.value["inline_mode"]
      preferred_port  = inline_mode_cfg.value["preferred_port"]
      preferred_trunk = inline_mode_cfg.value["preferred_trunk"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_vrrp_common.this.id
}

output "this" {
  value = thunder_vrrp_common.this
}
```

[top](#index)