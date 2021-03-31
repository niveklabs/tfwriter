# azurerm_virtual_hub_bgp_connection

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_virtual_hub_bgp_connection" {
  source = "./modules/azurerm/r/azurerm_virtual_hub_bgp_connection"

  # name - (required) is a type of string
  name = null
  # peer_asn - (required) is a type of number
  peer_asn = null
  # peer_ip - (required) is a type of string
  peer_ip = null
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "peer_asn" {
  description = "(required)"
  type        = number
}

variable "peer_ip" {
  description = "(required)"
  type        = string
}

variable "virtual_hub_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_virtual_hub_bgp_connection" "this" {
  name           = var.name
  peer_asn       = var.peer_asn
  peer_ip        = var.peer_ip
  virtual_hub_id = var.virtual_hub_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_virtual_hub_bgp_connection.this.id
}

output "this" {
  value = azurerm_virtual_hub_bgp_connection.this
}
```

[top](#index)