# azurerm_iothub_dps

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_iothub_dps" {
  source = "./modules/azurerm/d/azurerm_iothub_dps"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    read = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_iothub_dps" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allocation_policy" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps.this.allocation_policy
}

output "device_provisioning_host_name" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps.this.device_provisioning_host_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps.this.id
}

output "id_scope" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps.this.id_scope
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps.this.location
}

output "service_operations_host_name" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps.this.service_operations_host_name
}

output "this" {
  value = azurerm_iothub_dps.this
}
```

[top](#index)