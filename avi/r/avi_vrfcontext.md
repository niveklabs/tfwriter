# avi_vrfcontext

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_vrfcontext" {
  source = "./modules/avi/r/avi_vrfcontext"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # system_default - (optional) is a type of bool
  system_default = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  bgp_profile = [{
    community = []
    hold_time = null
    ibgp      = null
    ip_communities = [{
      community = []
      ip_begin = [{
        addr = null
        type = null
      }]
      ip_end = [{
        addr = null
        type = null
      }]
    }]
    keepalive_interval = null
    local_as           = null
    peers = [{
      advertise_snat_ip      = null
      advertise_vip          = null
      advertisement_interval = null
      bfd                    = null
      connect_timer          = null
      ebgp_multihop          = null
      hold_time              = null
      keepalive_interval     = null
      local_as               = null
      md5_secret             = null
      network_ref            = null
      peer_ip = [{
        addr = null
        type = null
      }]
      peer_ip6 = [{
        addr = null
        type = null
      }]
      remote_as = null
      shutdown  = null
      subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      subnet6 = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
    }]
    send_community = null
    shutdown       = null
  }]

  debugvrfcontext = [{
    command_buffer_interval = null
    command_buffer_size     = null
    flags = [{
      flag = null
    }]
  }]

  gateway_mon = [{
    gateway_ip = [{
      addr = null
      type = null
    }]
    gateway_monitor_fail_threshold    = null
    gateway_monitor_interval          = null
    gateway_monitor_success_threshold = null
    subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
  }]

  internal_gateway_monitor = [{
    disable_gateway_monitor           = null
    gateway_monitor_failure_threshold = null
    gateway_monitor_interval          = null
    gateway_monitor_success_threshold = null
  }]

  labels = [{
    key   = null
    value = null
  }]

  static_routes = [{
    disable_gateway_monitor = null
    if_name                 = null
    next_hop = [{
      addr = null
      type = null
    }]
    prefix = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    route_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "system_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      community = list(string)
      hold_time = number
      ibgp      = bool
      ip_communities = list(object(
        {
          community = list(string)
          ip_begin = set(object(
            {
              addr = string
              type = string
            }
          ))
          ip_end = set(object(
            {
              addr = string
              type = string
            }
          ))
        }
      ))
      keepalive_interval = number
      local_as           = number
      peers = list(object(
        {
          advertise_snat_ip      = bool
          advertise_vip          = bool
          advertisement_interval = number
          bfd                    = bool
          connect_timer          = number
          ebgp_multihop          = number
          hold_time              = number
          keepalive_interval     = number
          local_as               = number
          md5_secret             = string
          network_ref            = string
          peer_ip = set(object(
            {
              addr = string
              type = string
            }
          ))
          peer_ip6 = set(object(
            {
              addr = string
              type = string
            }
          ))
          remote_as = number
          shutdown  = bool
          subnet = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          subnet6 = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
        }
      ))
      send_community = bool
      shutdown       = bool
    }
  ))
  default = []
}

variable "debugvrfcontext" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      command_buffer_interval = number
      command_buffer_size     = number
      flags = list(object(
        {
          flag = string
        }
      ))
    }
  ))
  default = []
}

variable "gateway_mon" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      gateway_ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      gateway_monitor_fail_threshold    = number
      gateway_monitor_interval          = number
      gateway_monitor_success_threshold = number
      subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
    }
  ))
  default = []
}

variable "internal_gateway_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      disable_gateway_monitor           = bool
      gateway_monitor_failure_threshold = number
      gateway_monitor_interval          = number
      gateway_monitor_success_threshold = number
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "static_routes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      disable_gateway_monitor = bool
      if_name                 = string
      next_hop = set(object(
        {
          addr = string
          type = string
        }
      ))
      prefix = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      route_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_vrfcontext" "this" {
  cloud_ref      = var.cloud_ref
  description    = var.description
  name           = var.name
  system_default = var.system_default
  tenant_ref     = var.tenant_ref
  uuid           = var.uuid

  dynamic "bgp_profile" {
    for_each = var.bgp_profile
    content {
      community          = bgp_profile.value["community"]
      hold_time          = bgp_profile.value["hold_time"]
      ibgp               = bgp_profile.value["ibgp"]
      keepalive_interval = bgp_profile.value["keepalive_interval"]
      local_as           = bgp_profile.value["local_as"]
      send_community     = bgp_profile.value["send_community"]
      shutdown           = bgp_profile.value["shutdown"]

      dynamic "ip_communities" {
        for_each = bgp_profile.value.ip_communities
        content {
          community = ip_communities.value["community"]

          dynamic "ip_begin" {
            for_each = ip_communities.value.ip_begin
            content {
              addr = ip_begin.value["addr"]
              type = ip_begin.value["type"]
            }
          }

          dynamic "ip_end" {
            for_each = ip_communities.value.ip_end
            content {
              addr = ip_end.value["addr"]
              type = ip_end.value["type"]
            }
          }

        }
      }

      dynamic "peers" {
        for_each = bgp_profile.value.peers
        content {
          advertise_snat_ip      = peers.value["advertise_snat_ip"]
          advertise_vip          = peers.value["advertise_vip"]
          advertisement_interval = peers.value["advertisement_interval"]
          bfd                    = peers.value["bfd"]
          connect_timer          = peers.value["connect_timer"]
          ebgp_multihop          = peers.value["ebgp_multihop"]
          hold_time              = peers.value["hold_time"]
          keepalive_interval     = peers.value["keepalive_interval"]
          local_as               = peers.value["local_as"]
          md5_secret             = peers.value["md5_secret"]
          network_ref            = peers.value["network_ref"]
          remote_as              = peers.value["remote_as"]
          shutdown               = peers.value["shutdown"]

          dynamic "peer_ip" {
            for_each = peers.value.peer_ip
            content {
              addr = peer_ip.value["addr"]
              type = peer_ip.value["type"]
            }
          }

          dynamic "peer_ip6" {
            for_each = peers.value.peer_ip6
            content {
              addr = peer_ip6.value["addr"]
              type = peer_ip6.value["type"]
            }
          }

          dynamic "subnet" {
            for_each = peers.value.subnet
            content {
              mask = subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "subnet6" {
            for_each = peers.value.subnet6
            content {
              mask = subnet6.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet6.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "debugvrfcontext" {
    for_each = var.debugvrfcontext
    content {
      command_buffer_interval = debugvrfcontext.value["command_buffer_interval"]
      command_buffer_size     = debugvrfcontext.value["command_buffer_size"]

      dynamic "flags" {
        for_each = debugvrfcontext.value.flags
        content {
          flag = flags.value["flag"]
        }
      }

    }
  }

  dynamic "gateway_mon" {
    for_each = var.gateway_mon
    content {
      gateway_monitor_fail_threshold    = gateway_mon.value["gateway_monitor_fail_threshold"]
      gateway_monitor_interval          = gateway_mon.value["gateway_monitor_interval"]
      gateway_monitor_success_threshold = gateway_mon.value["gateway_monitor_success_threshold"]

      dynamic "gateway_ip" {
        for_each = gateway_mon.value.gateway_ip
        content {
          addr = gateway_ip.value["addr"]
          type = gateway_ip.value["type"]
        }
      }

      dynamic "subnet" {
        for_each = gateway_mon.value.subnet
        content {
          mask = subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "internal_gateway_monitor" {
    for_each = var.internal_gateway_monitor
    content {
      disable_gateway_monitor           = internal_gateway_monitor.value["disable_gateway_monitor"]
      gateway_monitor_failure_threshold = internal_gateway_monitor.value["gateway_monitor_failure_threshold"]
      gateway_monitor_interval          = internal_gateway_monitor.value["gateway_monitor_interval"]
      gateway_monitor_success_threshold = internal_gateway_monitor.value["gateway_monitor_success_threshold"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      key   = labels.value["key"]
      value = labels.value["value"]
    }
  }

  dynamic "static_routes" {
    for_each = var.static_routes
    content {
      disable_gateway_monitor = static_routes.value["disable_gateway_monitor"]
      if_name                 = static_routes.value["if_name"]
      route_id                = static_routes.value["route_id"]

      dynamic "next_hop" {
        for_each = static_routes.value.next_hop
        content {
          addr = next_hop.value["addr"]
          type = next_hop.value["type"]
        }
      }

      dynamic "prefix" {
        for_each = static_routes.value.prefix
        content {
          mask = prefix.value["mask"]

          dynamic "ip_addr" {
            for_each = prefix.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = avi_vrfcontext.this.cloud_ref
}

output "description" {
  description = "returns a string"
  value       = avi_vrfcontext.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_vrfcontext.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_vrfcontext.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_vrfcontext.this.uuid
}

output "this" {
  value = avi_vrfcontext.this
}
```

[top](#index)