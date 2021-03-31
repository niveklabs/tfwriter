# azurerm_data_factory_integration_runtime_azure

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
module "azurerm_data_factory_integration_runtime_azure" {
  source = "./modules/azurerm/r/azurerm_data_factory_integration_runtime_azure"

  # compute_type - (optional) is a type of string
  compute_type = null
  # core_count - (optional) is a type of number
  core_count = null
  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # time_to_live_min - (optional) is a type of number
  time_to_live_min = null

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
variable "compute_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "core_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "data_factory_name" {
  description = "(required)"
  type        = string
}

variable "description" {
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

variable "time_to_live_min" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "azurerm_data_factory_integration_runtime_azure" "this" {
  compute_type        = var.compute_type
  core_count          = var.core_count
  data_factory_name   = var.data_factory_name
  description         = var.description
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  time_to_live_min    = var.time_to_live_min

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
  value       = azurerm_data_factory_integration_runtime_azure.this.id
}

output "this" {
  value = azurerm_data_factory_integration_runtime_azure.this
}
```

[top](#index)