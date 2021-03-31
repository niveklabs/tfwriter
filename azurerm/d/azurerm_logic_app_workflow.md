# azurerm_logic_app_workflow

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_logic_app_workflow" {
  source = "./modules/azurerm/d/azurerm_logic_app_workflow"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
data "azurerm_logic_app_workflow" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "access_endpoint" {
  description = "returns a string"
  value       = data.azurerm_logic_app_workflow.this.access_endpoint
}

output "connector_endpoint_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_logic_app_workflow.this.connector_endpoint_ip_addresses
}

output "connector_outbound_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_logic_app_workflow.this.connector_outbound_ip_addresses
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_logic_app_workflow.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_logic_app_workflow.this.location
}

output "logic_app_integration_account_id" {
  description = "returns a string"
  value       = data.azurerm_logic_app_workflow.this.logic_app_integration_account_id
}

output "parameters" {
  description = "returns a map of string"
  value       = data.azurerm_logic_app_workflow.this.parameters
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_logic_app_workflow.this.tags
}

output "workflow_endpoint_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_logic_app_workflow.this.workflow_endpoint_ip_addresses
}

output "workflow_outbound_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_logic_app_workflow.this.workflow_outbound_ip_addresses
}

output "workflow_schema" {
  description = "returns a string"
  value       = data.azurerm_logic_app_workflow.this.workflow_schema
}

output "workflow_version" {
  description = "returns a string"
  value       = data.azurerm_logic_app_workflow.this.workflow_version
}

output "this" {
  value = azurerm_logic_app_workflow.this
}
```

[top](#index)