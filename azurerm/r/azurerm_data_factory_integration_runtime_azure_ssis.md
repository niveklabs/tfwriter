# azurerm_data_factory_integration_runtime_azure_ssis

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
module "azurerm_data_factory_integration_runtime_azure_ssis" {
  source = "./modules/azurerm/r/azurerm_data_factory_integration_runtime_azure_ssis"

  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # edition - (optional) is a type of string
  edition = null
  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # max_parallel_executions_per_node - (optional) is a type of number
  max_parallel_executions_per_node = null
  # name - (required) is a type of string
  name = null
  # node_size - (required) is a type of string
  node_size = null
  # number_of_nodes - (optional) is a type of number
  number_of_nodes = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  catalog_info = [{
    administrator_login    = null
    administrator_password = null
    pricing_tier           = null
    server_endpoint        = null
  }]

  custom_setup_script = [{
    blob_container_uri = null
    sas_token          = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  vnet_integration = [{
    subnet_name = null
    vnet_id     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data_factory_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "max_parallel_executions_per_node" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_size" {
  description = "(required)"
  type        = string
}

variable "number_of_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "catalog_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      administrator_login    = string
      administrator_password = string
      pricing_tier           = string
      server_endpoint        = string
    }
  ))
  default = []
}

variable "custom_setup_script" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      blob_container_uri = string
      sas_token          = string
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

variable "vnet_integration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      subnet_name = string
      vnet_id     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_data_factory_integration_runtime_azure_ssis" "this" {
  data_factory_name                = var.data_factory_name
  description                      = var.description
  edition                          = var.edition
  license_type                     = var.license_type
  location                         = var.location
  max_parallel_executions_per_node = var.max_parallel_executions_per_node
  name                             = var.name
  node_size                        = var.node_size
  number_of_nodes                  = var.number_of_nodes
  resource_group_name              = var.resource_group_name

  dynamic "catalog_info" {
    for_each = var.catalog_info
    content {
      administrator_login    = catalog_info.value["administrator_login"]
      administrator_password = catalog_info.value["administrator_password"]
      pricing_tier           = catalog_info.value["pricing_tier"]
      server_endpoint        = catalog_info.value["server_endpoint"]
    }
  }

  dynamic "custom_setup_script" {
    for_each = var.custom_setup_script
    content {
      blob_container_uri = custom_setup_script.value["blob_container_uri"]
      sas_token          = custom_setup_script.value["sas_token"]
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

  dynamic "vnet_integration" {
    for_each = var.vnet_integration
    content {
      subnet_name = vnet_integration.value["subnet_name"]
      vnet_id     = vnet_integration.value["vnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_data_factory_integration_runtime_azure_ssis.this.id
}

output "this" {
  value = azurerm_data_factory_integration_runtime_azure_ssis.this
}
```

[top](#index)