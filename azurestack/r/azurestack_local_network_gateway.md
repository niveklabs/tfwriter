# azurestack_local_network_gateway

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_local_network_gateway" {
  source = "./modules/azurestack/r/azurestack_local_network_gateway"

  # address_space - (required) is a type of list of string
  address_space = []
  # gateway_address - (required) is a type of string
  gateway_address = null
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
}
```

[top](#index)

### Variables

```terraform
variable "address_space" {
  description = "(required)"
  type        = list(string)
}

variable "gateway_address" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "azurestack_local_network_gateway" "this" {
  address_space       = var.address_space
  gateway_address     = var.gateway_address
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "bgp_settings" {
    for_each = var.bgp_settings
    content {
      asn                 = bgp_settings.value["asn"]
      bgp_peering_address = bgp_settings.value["bgp_peering_address"]
      peer_weight         = bgp_settings.value["peer_weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_local_network_gateway.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_local_network_gateway.this.tags
}

output "this" {
  value = azurestack_local_network_gateway.this
}
```

[top](#index)