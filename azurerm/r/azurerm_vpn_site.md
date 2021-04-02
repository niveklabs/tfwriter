# azurerm_vpn_site

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_vpn_site" {
  source = "./modules/azurerm/r/azurerm_vpn_site"

  # address_cidrs - (optional) is a type of set of string
  address_cidrs = []
  # device_model - (optional) is a type of string
  device_model = null
  # device_vendor - (optional) is a type of string
  device_vendor = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_wan_id - (required) is a type of string
  virtual_wan_id = null

  link = [{
    bgp = [{
      asn             = null
      peering_address = null
    }]
    fqdn          = null
    id            = null
    ip_address    = null
    name          = null
    provider_name = null
    speed_in_mbps = null
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
variable "address_cidrs" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "device_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_vendor" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_wan_id" {
  description = "(required)"
  type        = string
}

variable "link" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bgp = list(object(
        {
          asn             = number
          peering_address = string
        }
      ))
      fqdn          = string
      id            = string
      ip_address    = string
      name          = string
      provider_name = string
      speed_in_mbps = number
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
resource "azurerm_vpn_site" "this" {
  address_cidrs       = var.address_cidrs
  device_model        = var.device_model
  device_vendor       = var.device_vendor
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags
  virtual_wan_id      = var.virtual_wan_id

  dynamic "link" {
    for_each = var.link
    content {
      fqdn          = link.value["fqdn"]
      ip_address    = link.value["ip_address"]
      name          = link.value["name"]
      provider_name = link.value["provider_name"]
      speed_in_mbps = link.value["speed_in_mbps"]

      dynamic "bgp" {
        for_each = link.value.bgp
        content {
          asn             = bgp.value["asn"]
          peering_address = bgp.value["peering_address"]
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
  value       = azurerm_vpn_site.this.id
}

output "this" {
  value = azurerm_vpn_site.this
}
```

[top](#index)