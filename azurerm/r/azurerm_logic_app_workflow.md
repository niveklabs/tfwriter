# azurerm_logic_app_workflow

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
module "azurerm_logic_app_workflow" {
  source = "./modules/azurerm/r/azurerm_logic_app_workflow"

  # integration_service_environment_id - (optional) is a type of string
  integration_service_environment_id = null
  # location - (required) is a type of string
  location = null
  # logic_app_integration_account_id - (optional) is a type of string
  logic_app_integration_account_id = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # workflow_schema - (optional) is a type of string
  workflow_schema = null
  # workflow_version - (optional) is a type of string
  workflow_version = null

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
variable "integration_service_environment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "logic_app_integration_account_id" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "workflow_schema" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workflow_version" {
  description = "(optional)"
  type        = string
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
resource "azurerm_logic_app_workflow" "this" {
  integration_service_environment_id = var.integration_service_environment_id
  location                           = var.location
  logic_app_integration_account_id   = var.logic_app_integration_account_id
  name                               = var.name
  parameters                         = var.parameters
  resource_group_name                = var.resource_group_name
  tags                               = var.tags
  workflow_schema                    = var.workflow_schema
  workflow_version                   = var.workflow_version

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
output "access_endpoint" {
  description = "returns a string"
  value       = azurerm_logic_app_workflow.this.access_endpoint
}

output "connector_endpoint_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_logic_app_workflow.this.connector_endpoint_ip_addresses
}

output "connector_outbound_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_logic_app_workflow.this.connector_outbound_ip_addresses
}

output "id" {
  description = "returns a string"
  value       = azurerm_logic_app_workflow.this.id
}

output "workflow_endpoint_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_logic_app_workflow.this.workflow_endpoint_ip_addresses
}

output "workflow_outbound_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_logic_app_workflow.this.workflow_outbound_ip_addresses
}

output "this" {
  value = azurerm_logic_app_workflow.this
}
```

[top](#index)