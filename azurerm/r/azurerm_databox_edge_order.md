# azurerm_databox_edge_order

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
module "azurerm_databox_edge_order" {
  source = "./modules/azurerm/r/azurerm_databox_edge_order"

  # device_name - (required) is a type of string
  device_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  contact = [{
    company_name = null
    emails       = []
    name         = null
    phone_number = null
  }]

  shipment_address = [{
    address     = []
    city        = null
    country     = null
    postal_code = null
    state       = null
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
variable "device_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "contact" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      company_name = string
      emails       = set(string)
      name         = string
      phone_number = string
    }
  ))
}

variable "shipment_address" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      address     = list(string)
      city        = string
      country     = string
      postal_code = string
      state       = string
    }
  ))
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
resource "azurerm_databox_edge_order" "this" {
  device_name         = var.device_name
  resource_group_name = var.resource_group_name

  dynamic "contact" {
    for_each = var.contact
    content {
      company_name = contact.value["company_name"]
      emails       = contact.value["emails"]
      name         = contact.value["name"]
      phone_number = contact.value["phone_number"]
    }
  }

  dynamic "shipment_address" {
    for_each = var.shipment_address
    content {
      address     = shipment_address.value["address"]
      city        = shipment_address.value["city"]
      country     = shipment_address.value["country"]
      postal_code = shipment_address.value["postal_code"]
      state       = shipment_address.value["state"]
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
  value       = azurerm_databox_edge_order.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_databox_edge_order.this.name
}

output "return_tracking" {
  description = "returns a set of object"
  value       = azurerm_databox_edge_order.this.return_tracking
}

output "serial_number" {
  description = "returns a string"
  value       = azurerm_databox_edge_order.this.serial_number
}

output "shipment_history" {
  description = "returns a set of object"
  value       = azurerm_databox_edge_order.this.shipment_history
}

output "shipment_tracking" {
  description = "returns a set of object"
  value       = azurerm_databox_edge_order.this.shipment_tracking
}

output "status" {
  description = "returns a list of object"
  value       = azurerm_databox_edge_order.this.status
}

output "this" {
  value = azurerm_databox_edge_order.this
}
```

[top](#index)