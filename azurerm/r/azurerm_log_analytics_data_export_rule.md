# azurerm_log_analytics_data_export_rule

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
module "azurerm_log_analytics_data_export_rule" {
  source = "./modules/azurerm/r/azurerm_log_analytics_data_export_rule"

  # destination_resource_id - (required) is a type of string
  destination_resource_id = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # table_names - (required) is a type of set of string
  table_names = []
  # workspace_resource_id - (required) is a type of string
  workspace_resource_id = null

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
variable "destination_resource_id" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "table_names" {
  description = "(required)"
  type        = set(string)
}

variable "workspace_resource_id" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_log_analytics_data_export_rule" "this" {
  # destination_resource_id - (required) is a type of string
  destination_resource_id = var.destination_resource_id
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # table_names - (required) is a type of set of string
  table_names = var.table_names
  # workspace_resource_id - (required) is a type of string
  workspace_resource_id = var.workspace_resource_id

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
output "export_rule_id" {
  description = "returns a string"
  value       = azurerm_log_analytics_data_export_rule.this.export_rule_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_log_analytics_data_export_rule.this.id
}

output "this" {
  value = azurerm_log_analytics_data_export_rule.this
}
```

[top](#index)