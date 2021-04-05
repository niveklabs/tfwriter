# thunder_vrrp_vrid

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
module "thunder_vrrp_vrid" {
  source = "./modules/thunder/r/thunder_vrrp_vrid"

  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrid_val - (optional) is a type of number
  vrid_val = null

  blade_parameters = [{
    fail_over_policy_template = null
    priority                  = null
    tracking_options = [{
      bgp = [{
        bgp_ipv4_address_cfg = [{
          bgp_ipv4_address = null
          priority_cost    = null
        }]
        bgp_ipv6_address_cfg = [{
          bgp_ipv6_address = null
          priority_cost    = null
        }]
      }]
      gateway = [{
        ipv4_gateway_list = [{
          ip_address    = null
          priority_cost = null
          uuid          = null
        }]
        ipv6_gateway_list = [{
          ipv6_address  = null
          priority_cost = null
          uuid          = null
        }]
      }]
      interface = [{
        ethernet      = null
        priority_cost = null
      }]
      route = [{
        ip_destination_cfg = [{
          distance       = null
          gateway        = null
          ip_destination = null
          mask           = null
          priority_cost  = null
          protocol       = null
        }]
        ipv6_destination_cfg = [{
          distance         = null
          gatewayv6        = null
          ipv6_destination = null
          priority_cost    = null
          protocol         = null
        }]
      }]
      trunk_cfg = [{
        per_port_pri  = null
        priority_cost = null
        trunk         = null
      }]
      uuid = null
      vlan_cfg = [{
        priority_cost = null
        timeout       = null
        vlan          = null
      }]
    }]
    uuid = null
  }]

  floating_ip = [{
    ip_address_cfg = [{
      ip_address = null
    }]
    ip_address_part_cfg = [{
      ip_address_partition = null
    }]
    ipv6_address_cfg = [{
      ethernet     = null
      ipv6_address = null
      trunk        = null
      ve           = null
    }]
    ipv6_address_part_cfg = [{
      ethernet               = null
      ipv6_address_partition = null
      trunk                  = null
      ve                     = null
    }]
  }]

  follow = [{
    vrid_lead = null
  }]

  preempt_mode = [{
    disable   = null
    threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrid_val" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "blade_parameters" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fail_over_policy_template = string
      priority                  = number
      tracking_options = list(object(
        {
          bgp = list(object(
            {
              bgp_ipv4_address_cfg = list(object(
                {
                  bgp_ipv4_address = string
                  priority_cost    = number
                }
              ))
              bgp_ipv6_address_cfg = list(object(
                {
                  bgp_ipv6_address = string
                  priority_cost    = number
                }
              ))
            }
          ))
          gateway = list(object(
            {
              ipv4_gateway_list = list(object(
                {
                  ip_address    = string
                  priority_cost = number
                  uuid          = string
                }
              ))
              ipv6_gateway_list = list(object(
                {
                  ipv6_address  = string
                  priority_cost = number
                  uuid          = string
                }
              ))
            }
          ))
          interface = list(object(
            {
              ethernet      = number
              priority_cost = number
            }
          ))
          route = list(object(
            {
              ip_destination_cfg = list(object(
                {
                  distance       = number
                  gateway        = string
                  ip_destination = string
                  mask           = string
                  priority_cost  = number
                  protocol       = string
                }
              ))
              ipv6_destination_cfg = list(object(
                {
                  distance         = number
                  gatewayv6        = string
                  ipv6_destination = string
                  priority_cost    = number
                  protocol         = string
                }
              ))
            }
          ))
          trunk_cfg = list(object(
            {
              per_port_pri  = number
              priority_cost = number
              trunk         = number
            }
          ))
          uuid = string
          vlan_cfg = list(object(
            {
              priority_cost = number
              timeout       = number
              vlan          = number
            }
          ))
        }
      ))
      uuid = string
    }
  ))
  default = []
}

variable "floating_ip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_address_cfg = list(object(
        {
          ip_address = string
        }
      ))
      ip_address_part_cfg = list(object(
        {
          ip_address_partition = string
        }
      ))
      ipv6_address_cfg = list(object(
        {
          ethernet     = number
          ipv6_address = string
          trunk        = number
          ve           = number
        }
      ))
      ipv6_address_part_cfg = list(object(
        {
          ethernet               = number
          ipv6_address_partition = string
          trunk                  = number
          ve                     = number
        }
      ))
    }
  ))
  default = []
}

variable "follow" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      vrid_lead = string
    }
  ))
  default = []
}

variable "preempt_mode" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable   = number
      threshold = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_vrrp_vrid" "this" {
  user_tag = var.user_tag
  uuid     = var.uuid
  vrid_val = var.vrid_val

  dynamic "blade_parameters" {
    for_each = var.blade_parameters
    content {
      fail_over_policy_template = blade_parameters.value["fail_over_policy_template"]
      priority                  = blade_parameters.value["priority"]
      uuid                      = blade_parameters.value["uuid"]

      dynamic "tracking_options" {
        for_each = blade_parameters.value.tracking_options
        content {
          uuid = tracking_options.value["uuid"]

          dynamic "bgp" {
            for_each = tracking_options.value.bgp
            content {

              dynamic "bgp_ipv4_address_cfg" {
                for_each = bgp.value.bgp_ipv4_address_cfg
                content {
                  bgp_ipv4_address = bgp_ipv4_address_cfg.value["bgp_ipv4_address"]
                  priority_cost    = bgp_ipv4_address_cfg.value["priority_cost"]
                }
              }

              dynamic "bgp_ipv6_address_cfg" {
                for_each = bgp.value.bgp_ipv6_address_cfg
                content {
                  bgp_ipv6_address = bgp_ipv6_address_cfg.value["bgp_ipv6_address"]
                  priority_cost    = bgp_ipv6_address_cfg.value["priority_cost"]
                }
              }

            }
          }

          dynamic "gateway" {
            for_each = tracking_options.value.gateway
            content {

              dynamic "ipv4_gateway_list" {
                for_each = gateway.value.ipv4_gateway_list
                content {
                  ip_address    = ipv4_gateway_list.value["ip_address"]
                  priority_cost = ipv4_gateway_list.value["priority_cost"]
                  uuid          = ipv4_gateway_list.value["uuid"]
                }
              }

              dynamic "ipv6_gateway_list" {
                for_each = gateway.value.ipv6_gateway_list
                content {
                  ipv6_address  = ipv6_gateway_list.value["ipv6_address"]
                  priority_cost = ipv6_gateway_list.value["priority_cost"]
                  uuid          = ipv6_gateway_list.value["uuid"]
                }
              }

            }
          }

          dynamic "interface" {
            for_each = tracking_options.value.interface
            content {
              ethernet      = interface.value["ethernet"]
              priority_cost = interface.value["priority_cost"]
            }
          }

          dynamic "route" {
            for_each = tracking_options.value.route
            content {

              dynamic "ip_destination_cfg" {
                for_each = route.value.ip_destination_cfg
                content {
                  distance       = ip_destination_cfg.value["distance"]
                  gateway        = ip_destination_cfg.value["gateway"]
                  ip_destination = ip_destination_cfg.value["ip_destination"]
                  mask           = ip_destination_cfg.value["mask"]
                  priority_cost  = ip_destination_cfg.value["priority_cost"]
                  protocol       = ip_destination_cfg.value["protocol"]
                }
              }

              dynamic "ipv6_destination_cfg" {
                for_each = route.value.ipv6_destination_cfg
                content {
                  distance         = ipv6_destination_cfg.value["distance"]
                  gatewayv6        = ipv6_destination_cfg.value["gatewayv6"]
                  ipv6_destination = ipv6_destination_cfg.value["ipv6_destination"]
                  priority_cost    = ipv6_destination_cfg.value["priority_cost"]
                  protocol         = ipv6_destination_cfg.value["protocol"]
                }
              }

            }
          }

          dynamic "trunk_cfg" {
            for_each = tracking_options.value.trunk_cfg
            content {
              per_port_pri  = trunk_cfg.value["per_port_pri"]
              priority_cost = trunk_cfg.value["priority_cost"]
              trunk         = trunk_cfg.value["trunk"]
            }
          }

          dynamic "vlan_cfg" {
            for_each = tracking_options.value.vlan_cfg
            content {
              priority_cost = vlan_cfg.value["priority_cost"]
              timeout       = vlan_cfg.value["timeout"]
              vlan          = vlan_cfg.value["vlan"]
            }
          }

        }
      }

    }
  }

  dynamic "floating_ip" {
    for_each = var.floating_ip
    content {

      dynamic "ip_address_cfg" {
        for_each = floating_ip.value.ip_address_cfg
        content {
          ip_address = ip_address_cfg.value["ip_address"]
        }
      }

      dynamic "ip_address_part_cfg" {
        for_each = floating_ip.value.ip_address_part_cfg
        content {
          ip_address_partition = ip_address_part_cfg.value["ip_address_partition"]
        }
      }

      dynamic "ipv6_address_cfg" {
        for_each = floating_ip.value.ipv6_address_cfg
        content {
          ethernet     = ipv6_address_cfg.value["ethernet"]
          ipv6_address = ipv6_address_cfg.value["ipv6_address"]
          trunk        = ipv6_address_cfg.value["trunk"]
          ve           = ipv6_address_cfg.value["ve"]
        }
      }

      dynamic "ipv6_address_part_cfg" {
        for_each = floating_ip.value.ipv6_address_part_cfg
        content {
          ethernet               = ipv6_address_part_cfg.value["ethernet"]
          ipv6_address_partition = ipv6_address_part_cfg.value["ipv6_address_partition"]
          trunk                  = ipv6_address_part_cfg.value["trunk"]
          ve                     = ipv6_address_part_cfg.value["ve"]
        }
      }

    }
  }

  dynamic "follow" {
    for_each = var.follow
    content {
      vrid_lead = follow.value["vrid_lead"]
    }
  }

  dynamic "preempt_mode" {
    for_each = var.preempt_mode
    content {
      disable   = preempt_mode.value["disable"]
      threshold = preempt_mode.value["threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_vrrp_vrid.this.id
}

output "this" {
  value = thunder_vrrp_vrid.this
}
```

[top](#index)