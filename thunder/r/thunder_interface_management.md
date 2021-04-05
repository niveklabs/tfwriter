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
  action       = var.action
  duplexity    = var.duplexity
  flow_control = var.flow_control
  speed        = var.speed
  uuid         = var.uuid

  dynamic "access_list" {
    for_each = var.access_list
    content {
      acl_id   = access_list.value["acl_id"]
      acl_name = access_list.value["acl_name"]
    }
  }

  dynamic "broadcast_rate_limit" {
    for_each = var.broadcast_rate_limit
    content {
      bcast_rate_limit_enable = broadcast_rate_limit.value["bcast_rate_limit_enable"]
      rate                    = broadcast_rate_limit.value["rate"]
    }
  }

  dynamic "ip" {
    for_each = var.ip
    content {
      control_apps_use_mgmt_port = ip.value["control_apps_use_mgmt_port"]
      default_gateway            = ip.value["default_gateway"]
      dhcp                       = ip.value["dhcp"]
      ipv4_address               = ip.value["ipv4_address"]
      ipv4_netmask               = ip.value["ipv4_netmask"]
    }
  }

  dynamic "ipv6" {
    for_each = var.ipv6
    content {
      address_type         = ipv6.value["address_type"]
      default_ipv6_gateway = ipv6.value["default_ipv6_gateway"]
      inbound              = ipv6.value["inbound"]
      ipv6_addr            = ipv6.value["ipv6_addr"]
      v6_acl_name          = ipv6.value["v6_acl_name"]
    }
  }

  dynamic "lldp" {
    for_each = var.lldp
    content {
      uuid = lldp.value["uuid"]

      dynamic "enable_cfg" {
        for_each = lldp.value.enable_cfg
        content {
          rt_enable = enable_cfg.value["rt_enable"]
          rx        = enable_cfg.value["rx"]
          tx        = enable_cfg.value["tx"]
        }
      }

      dynamic "notification_cfg" {
        for_each = lldp.value.notification_cfg
        content {
          notif_enable = notification_cfg.value["notif_enable"]
          notification = notification_cfg.value["notification"]
        }
      }

      dynamic "tx_dot1_cfg" {
        for_each = lldp.value.tx_dot1_cfg
        content {
          link_aggregation = tx_dot1_cfg.value["link_aggregation"]
          tx_dot1_tlvs     = tx_dot1_cfg.value["tx_dot1_tlvs"]
          vlan             = tx_dot1_cfg.value["vlan"]
        }
      }

      dynamic "tx_tlvs_cfg" {
        for_each = lldp.value.tx_tlvs_cfg
        content {
          exclude             = tx_tlvs_cfg.value["exclude"]
          management_address  = tx_tlvs_cfg.value["management_address"]
          port_description    = tx_tlvs_cfg.value["port_description"]
          system_capabilities = tx_tlvs_cfg.value["system_capabilities"]
          system_description  = tx_tlvs_cfg.value["system_description"]
          system_name         = tx_tlvs_cfg.value["system_name"]
          tx_tlvs             = tx_tlvs_cfg.value["tx_tlvs"]
        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

  dynamic "secondary_ip" {
    for_each = var.secondary_ip
    content {
      control_apps_use_mgmt_port = secondary_ip.value["control_apps_use_mgmt_port"]
      default_gateway            = secondary_ip.value["default_gateway"]
      dhcp                       = secondary_ip.value["dhcp"]
      ipv4_address               = secondary_ip.value["ipv4_address"]
      ipv4_netmask               = secondary_ip.value["ipv4_netmask"]
      secondary_ip               = secondary_ip.value["secondary_ip"]
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