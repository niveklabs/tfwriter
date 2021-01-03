# azurerm_iothub_dps

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
module "azurerm_iothub_dps" {
  source = "./modules/azurerm/r/azurerm_iothub_dps"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  linked_hub = [{
    allocation_weight       = null
    apply_allocation_policy = null
    connection_string       = null
    hostname                = null
    location                = null
  }]

  sku = [{
    capacity = null
    name     = null
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "linked_hub" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allocation_weight       = number
      apply_allocation_policy = bool
      connection_string       = string
      hostname                = string
      location                = string
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      name     = string
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
resource "azurerm_iothub_dps" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "linked_hub" {
    for_each = var.linked_hub
    content {
      allocation_weight       = linked_hub.value["allocation_weight"]
      apply_allocation_policy = linked_hub.value["apply_allocation_policy"]
      connection_string       = linked_hub.value["connection_string"]
      location                = linked_hub.value["location"]
    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      capacity = sku.value["capacity"]
      name     = sku.value["name"]
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
output "allocation_policy" {
  description = "returns a string"
  value       = azurerm_iothub_dps.this.allocation_policy
}

output "device_provisioning_host_name" {
  description = "returns a string"
  value       = azurerm_iothub_dps.this.device_provisioning_host_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_iothub_dps.this.id
}

output "id_scope" {
  description = "returns a string"
  value       = azurerm_iothub_dps.this.id_scope
}

output "service_operations_host_name" {
  description = "returns a string"
  value       = azurerm_iothub_dps.this.service_operations_host_name
}

output "this" {
  value = azurerm_iothub_dps.this
}
```

[top](#index)