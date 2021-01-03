# azurerm_vpn_gateway

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_vpn_gateway" {
  source = "./modules/azurerm/r/azurerm_vpn_gateway"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scale_unit - (optional) is a type of number
  scale_unit = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = null

  bgp_settings = [{
    asn                 = null
    bgp_peering_address = null
    instance_0_bgp_peering_address = [{
      custom_ips          = []
      default_ips         = []
      ip_configuration_id = null
      tunnel_ips          = []
    }]
    instance_1_bgp_peering_address = [{
      custom_ips          = []
      default_ips         = []
      ip_configuration_id = null
      tunnel_ips          = []
    }]
    peer_weight = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "scale_unit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_hub_id" {
  description = "(required)"
  type        = string
}

variable "bgp_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      asn                 = number
      bgp_peering_address = string
      instance_0_bgp_peering_address = list(object(
        {
          custom_ips          = set(string)
          default_ips         = set(string)
          ip_configuration_id = string
          tunnel_ips          = set(string)
        }
      ))
      instance_1_bgp_peering_address = list(object(
        {
          custom_ips          = set(string)
          default_ips         = set(string)
          ip_configuration_id = string
          tunnel_ips          = set(string)
        }
      ))
      peer_weight = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_vpn_gateway" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  scale_unit          = var.scale_unit
  tags                = var.tags
  virtual_hub_id      = var.virtual_hub_id

  dynamic "bgp_settings" {
    for_each = var.bgp_settings
    content {
      asn         = bgp_settings.value["asn"]
      peer_weight = bgp_settings.value["peer_weight"]

      dynamic "instance_0_bgp_peering_address" {
        for_each = bgp_settings.value.instance_0_bgp_peering_address
        content {
          custom_ips = instance_0_bgp_peering_address.value["custom_ips"]
        }
      }

      dynamic "instance_1_bgp_peering_address" {
        for_each = bgp_settings.value.instance_1_bgp_peering_address
        content {
          custom_ips = instance_1_bgp_peering_address.value["custom_ips"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_vpn_gateway.this.id
}

output "this" {
  value = azurerm_vpn_gateway.this
}
```

[top](#index)