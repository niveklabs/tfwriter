# azurerm_data_factory_linked_service_data_lake_storage_gen2

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
module "azurerm_data_factory_linked_service_data_lake_storage_gen2" {
  source = "./modules/azurerm/r/azurerm_data_factory_linked_service_data_lake_storage_gen2"

  # additional_properties - (optional) is a type of map of string
  additional_properties = {}
  # annotations - (optional) is a type of list of string
  annotations = []
  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # integration_runtime_name - (optional) is a type of string
  integration_runtime_name = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_principal_id - (optional) is a type of string
  service_principal_id = null
  # service_principal_key - (optional) is a type of string
  service_principal_key = null
  # tenant - (optional) is a type of string
  tenant = null
  # url - (required) is a type of string
  url = null
  # use_managed_identity - (optional) is a type of bool
  use_managed_identity = null

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
variable "additional_properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "annotations" {
  description = "(optional)"
  type        = list(string)
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

variable "integration_runtime_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_principal_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_principal_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "use_managed_identity" {
  description = "(optional)"
  type        = bool
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
resource "azurerm_data_factory_linked_service_data_lake_storage_gen2" "this" {
  additional_properties    = var.additional_properties
  annotations              = var.annotations
  data_factory_name        = var.data_factory_name
  description              = var.description
  integration_runtime_name = var.integration_runtime_name
  name                     = var.name
  parameters               = var.parameters
  resource_group_name      = var.resource_group_name
  service_principal_id     = var.service_principal_id
  service_principal_key    = var.service_principal_key
  tenant                   = var.tenant
  url                      = var.url
  use_managed_identity     = var.use_managed_identity

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
  value       = azurerm_data_factory_linked_service_data_lake_storage_gen2.this.id
}

output "this" {
  value = azurerm_data_factory_linked_service_data_lake_storage_gen2.this
}
```

[top](#index)