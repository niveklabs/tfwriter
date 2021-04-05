# thunder_interface_ethernet_lldp

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
module "thunder_interface_ethernet_lldp" {
  source = "./modules/thunder/r/thunder_interface_ethernet_lldp"

  # ifnum - (optional) is a type of number
  ifnum = null
  # uuid - (optional) is a type of string
  uuid = null

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
}
```

[top](#index)

### Variables

```terraform
variable "ifnum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      rt_enable = number
      rx        = number
      tx        = number
    }
  ))
  default = []
}

variable "notification_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      notif_enable = number
      notification = number
    }
  ))
  default = []
}

variable "tx_dot1_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      link_aggregation = number
      tx_dot1_tlvs     = number
      vlan             = number
    }
  ))
  default = []
}

variable "tx_tlvs_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_interface_ethernet_lldp" "this" {
  ifnum = var.ifnum
  uuid  = var.uuid

  dynamic "enable_cfg" {
    for_each = var.enable_cfg
    content {
      rt_enable = enable_cfg.value["rt_enable"]
      rx        = enable_cfg.value["rx"]
      tx        = enable_cfg.value["tx"]
    }
  }

  dynamic "notification_cfg" {
    for_each = var.notification_cfg
    content {
      notif_enable = notification_cfg.value["notif_enable"]
      notification = notification_cfg.value["notification"]
    }
  }

  dynamic "tx_dot1_cfg" {
    for_each = var.tx_dot1_cfg
    content {
      link_aggregation = tx_dot1_cfg.value["link_aggregation"]
      tx_dot1_tlvs     = tx_dot1_cfg.value["tx_dot1_tlvs"]
      vlan             = tx_dot1_cfg.value["vlan"]
    }
  }

  dynamic "tx_tlvs_cfg" {
    for_each = var.tx_tlvs_cfg
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
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_ethernet_lldp.this.id
}

output "this" {
  value = thunder_interface_ethernet_lldp.this
}
```

[top](#index)