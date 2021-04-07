# azurerm_local_network_gateway

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
module "azurerm_local_network_gateway" {
  source = "./modules/azurerm/r/azurerm_local_network_gateway"

  # address_space - (optional) is a type of list of string
  address_space = []
  # gateway_address - (optional) is a type of string
  gateway_address = null
  # gateway_fqdn - (optional) is a type of string
  gateway_fqdn = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  bgp_settings = [{
    asn                 = null
    bgp_peering_address = null
    peer_weight         = null
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
variable "address_space" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "gateway_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_fqdn" {
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

variable "bgp_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      asn                 = number
      bgp_peering_address = string
      peer_weight         = number
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
resource "azurerm_local_network_gateway" "this" {
  # address_space - (optional) is a type of list of string
  address_space = var.address_space
  # gateway_address - (optional) is a type of string
  gateway_address = var.gateway_address
  # gateway_fqdn - (optional) is a type of string
  gateway_fqdn = var.gateway_fqdn
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "bgp_settings" {
    for_each = var.bgp_settings
    content {
      # asn - (required) is a type of number
      asn = bgp_settings.value["asn"]
      # bgp_peering_address - (required) is a type of string
      bgp_peering_address = bgp_settings.value["bgp_peering_address"]
      # peer_weight - (optional) is a type of number
      peer_weight = bgp_settings.value["peer_weight"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azurerm_local_network_gateway.this.id
}

output "this" {
  value = azurerm_local_network_gateway.this
}
```

[top](#index)