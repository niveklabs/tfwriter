# thunder_interface_management

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
module "thunder_interface_management" {
  source = "./modules/thunder/r/thunder_interface_management"

  # action - (optional) is a type of string
  action = null
  # duplexity - (optional) is a type of string
  duplexity = null
  # flow_control - (optional) is a type of number
  flow_control = null
  # speed - (optional) is a type of string
  speed = null
  # uuid - (optional) is a type of string
  uuid = null

  access_list = [{
    acl_id   = null
    acl_name = null
  }]

  broadcast_rate_limit = [{
    bcast_rate_limit_enable = null
    rate                    = null
  }]

  ip = [{
    control_apps_use_mgmt_port = null
    default_gateway            = null
    dhcp                       = null
    ipv4_address               = null
    ipv4_netmask               = null
  }]

  ipv6 = [{
    address_type         = null
    default_ipv6_gateway = null
    inbound              = null
    ipv6_addr            = null
    v6_acl_name          = null
  }]

  lldp = [{
    enable_cfg = [{
      rt_enable = null
      rx        = null
      tx        = null
    }]
    notification_cfg = [{
      notif_enable = null
      notification = null
    }]
    tx_dot1_cfg = [{
      link_aggregation = null
      tx_dot1_tlvs     = null
      vlan             = null
    }]
    tx_tlvs_cfg = [{
      exclude             = null
      management_address  = null
      port_description    = null
      system_capabilities = null
      system_description  = null
      system_name         = null
      tx_tlvs             = null
    }]
    uuid = null
  }]

  sampling_enable = [{
    counters1 = null
  }]

  secondary_ip = [{
    control_apps_use_mgmt_port = null
    default_gateway            = null
    dhcp                       = null
    ipv4_address               = null
    ipv4_netmask               = null
    secondary_ip               = null
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

variable "duplexity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_control" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "speed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_list" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      acl_id   = number
      acl_name = string
    }
  ))
  default = []
}

variable "broadcast_rate_limit" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bcast_rate_limit_enable = number
      rate                    = number
    }
  ))
  default = []
}

variable "ip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      control_apps_use_mgmt_port = number
      default_gateway            = string
      dhcp                       = number
      ipv4_address               = string
      ipv4_netmask               = string
    }
  ))
  default = []
}

variable "ipv6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      address_type         = string
      default_ipv6_gateway = string
      inbound              = number
      ipv6_addr            = string
      v6_acl_name          = string
    }
  ))
  default = []
}

variable "lldp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_cfg = list(object(
        {
          rt_enable = number
          rx        = number
          tx        = number
        }
      ))
      notification_cfg = list(object(
        {
          notif_enable = number
          notification = number
        }
      ))
      tx_dot1_cfg = list(object(
        {
          link_aggregation = number
          tx_dot1_tlvs     = number
          vlan             = number
        }
      ))
      tx_tlvs_cfg = list(object(
        {
          exclude             = number
          management_address  = number
          port_description    = number
          system_capabilities = number
          system_description  = number
          system_name         = number
          tx_tlvs             = number
        }
      ))
      uuid = string
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}

variable "secondary_ip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      control_apps_use_mgmt_port = number
      default_gateway            = string
      dhcp                       = number
      ipv4_address               = string
      ipv4_netmask               = string
      secondary_ip               = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_interface_management" "this" {
  # action - (optional) is a type of string
  action = var.action
  # duplexity - (optional) is a type of string
  duplexity = var.duplexity
  # flow_control - (optional) is a type of number
  flow_control = var.flow_control
  # speed - (optional) is a type of string
  speed = var.speed
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "access_list" {
    for_each = var.access_list
    content {
      # acl_id - (optional) is a type of number
      acl_id = access_list.value["acl_id"]
      # acl_name - (optional) is a type of string
      acl_name = access_list.value["acl_name"]
    }
  }

  dynamic "broadcast_rate_limit" {
    for_each = var.broadcast_rate_limit
    content {
      # bcast_rate_limit_enable - (optional) is a type of number
      bcast_rate_limit_enable = broadcast_rate_limit.value["bcast_rate_limit_enable"]
      # rate - (optional) is a type of number
      rate = broadcast_rate_limit.value["rate"]
    }
  }

  dynamic "ip" {
    for_each = var.ip
    content {
      # control_apps_use_mgmt_port - (optional) is a type of number
      control_apps_use_mgmt_port = ip.value["control_apps_use_mgmt_port"]
      # default_gateway - (optional) is a type of string
      default_gateway = ip.value["default_gateway"]
      # dhcp - (optional) is a type of number
      dhcp = ip.value["dhcp"]
      # ipv4_address - (optional) is a type of string
      ipv4_address = ip.value["ipv4_address"]
      # ipv4_netmask - (optional) is a type of string
      ipv4_netmask = ip.value["ipv4_netmask"]
    }
  }

  dynamic "ipv6" {
    for_each = var.ipv6
    content {
      # address_type - (optional) is a type of string
      address_type = ipv6.value["address_type"]
      # default_ipv6_gateway - (optional) is a type of string
      default_ipv6_gateway = ipv6.value["default_ipv6_gateway"]
      # inbound - (optional) is a type of number
      inbound = ipv6.value["inbound"]
      # ipv6_addr - (optional) is a type of string
      ipv6_addr = ipv6.value["ipv6_addr"]
      # v6_acl_name - (optional) is a type of string
      v6_acl_name = ipv6.value["v6_acl_name"]
    }
  }

  dynamic "lldp" {
    for_each = var.lldp
    content {
      # uuid - (optional) is a type of string
      uuid = lldp.value["uuid"]

      dynamic "enable_cfg" {
        for_each = lldp.value.enable_cfg
        content {
          # rt_enable - (optional) is a type of number
          rt_enable = enable_cfg.value["rt_enable"]
          # rx - (optional) is a type of number
          rx = enable_cfg.value["rx"]
          # tx - (optional) is a type of number
          tx = enable_cfg.value["tx"]
        }
      }

      dynamic "notification_cfg" {
        for_each = lldp.value.notification_cfg
        content {
          # notif_enable - (optional) is a type of number
          notif_enable = notification_cfg.value["notif_enable"]
          # notification - (optional) is a type of number
          notification = notification_cfg.value["notification"]
        }
      }

      dynamic "tx_dot1_cfg" {
        for_each = lldp.value.tx_dot1_cfg
        content {
          # link_aggregation - (optional) is a type of number
          link_aggregation = tx_dot1_cfg.value["link_aggregation"]
          # tx_dot1_tlvs - (optional) is a type of number
          tx_dot1_tlvs = tx_dot1_cfg.value["tx_dot1_tlvs"]
          # vlan - (optional) is a type of number
          vlan = tx_dot1_cfg.value["vlan"]
        }
      }

      dynamic "tx_tlvs_cfg" {
        for_each = lldp.value.tx_tlvs_cfg
        content {
          # exclude - (optional) is a type of number
          exclude = tx_tlvs_cfg.value["exclude"]
          # management_address - (optional) is a type of number
          management_address = tx_tlvs_cfg.value["management_address"]
          # port_description - (optional) is a type of number
          port_description = tx_tlvs_cfg.value["port_description"]
          # system_capabilities - (optional) is a type of number
          system_capabilities = tx_tlvs_cfg.value["system_capabilities"]
          # system_description - (optional) is a type of number
          system_description = tx_tlvs_cfg.value["system_description"]
          # system_name - (optional) is a type of number
          system_name = tx_tlvs_cfg.value["system_name"]
          # tx_tlvs - (optional) is a type of number
          tx_tlvs = tx_tlvs_cfg.value["tx_tlvs"]
        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      # counters1 - (optional) is a type of string
      counters1 = sampling_enable.value["counters1"]
    }
  }

  dynamic "secondary_ip" {
    for_each = var.secondary_ip
    content {
      # control_apps_use_mgmt_port - (optional) is a type of number
      control_apps_use_mgmt_port = secondary_ip.value["control_apps_use_mgmt_port"]
      # default_gateway - (optional) is a type of string
      default_gateway = secondary_ip.value["default_gateway"]
      # dhcp - (optional) is a type of number
      dhcp = secondary_ip.value["dhcp"]
      # ipv4_address - (optional) is a type of string
      ipv4_address = secondary_ip.value["ipv4_address"]
      # ipv4_netmask - (optional) is a type of string
      ipv4_netmask = secondary_ip.value["ipv4_netmask"]
      # secondary_ip - (optional) is a type of number
      secondary_ip = secondary_ip.value["secondary_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_management.this.id
}

output "this" {
  value = thunder_interface_management.this
}
```

[top](#index)