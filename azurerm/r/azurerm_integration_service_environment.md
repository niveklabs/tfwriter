# azurerm_integration_service_environment

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
module "azurerm_integration_service_environment" {
  source = "./modules/azurerm/r/azurerm_integration_service_environment"

  # access_endpoint_type - (required) is a type of string
  access_endpoint_type = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (optional) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_network_subnet_ids - (required) is a type of set of string
  virtual_network_subnet_ids = []

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
variable "access_endpoint_type" {
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

variable "sku_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_network_subnet_ids" {
  description = "(required)"
  type        = set(string)
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
resource "azurerm_integration_service_environment" "this" {
  # access_endpoint_type - (required) is a type of string
  access_endpoint_type = var.access_endpoint_type
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku_name - (optional) is a type of string
  sku_name = var.sku_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # virtual_network_subnet_ids - (required) is a type of set of string
  virtual_network_subnet_ids = var.virtual_network_subnet_ids

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
output "connector_endpoint_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_integration_service_environment.this.connector_endpoint_ip_addresses
}

output "connector_outbound_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_integration_service_environment.this.connector_outbound_ip_addresses
}

output "id" {
  description = "returns a string"
  value       = azurerm_integration_service_environment.this.id
}

output "workflow_endpoint_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_integration_service_environment.this.workflow_endpoint_ip_addresses
}

output "workflow_outbound_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_integration_service_environment.this.workflow_outbound_ip_addresses
}

output "this" {
  value = azurerm_integration_service_environment.this
}
```

[top](#index)