# azurerm_log_analytics_workspace

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
module "azurerm_log_analytics_workspace" {
  source = "./modules/azurerm/r/azurerm_log_analytics_workspace"

  # daily_quota_gb - (optional) is a type of number
  daily_quota_gb = null
  # internet_ingestion_enabled - (optional) is a type of bool
  internet_ingestion_enabled = null
  # internet_query_enabled - (optional) is a type of bool
  internet_query_enabled = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # reservation_capcity_in_gb_per_day - (optional) is a type of number
  reservation_capcity_in_gb_per_day = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # retention_in_days - (optional) is a type of number
  retention_in_days = null
  # sku - (optional) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "daily_quota_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internet_ingestion_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "internet_query_enabled" {
  description = "(optional)"
  type        = bool
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

variable "reservation_capcity_in_gb_per_day" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "retention_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sku" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_log_analytics_workspace" "this" {
  # daily_quota_gb - (optional) is a type of number
  daily_quota_gb = var.daily_quota_gb
  # internet_ingestion_enabled - (optional) is a type of bool
  internet_ingestion_enabled = var.internet_ingestion_enabled
  # internet_query_enabled - (optional) is a type of bool
  internet_query_enabled = var.internet_query_enabled
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # reservation_capcity_in_gb_per_day - (optional) is a type of number
  reservation_capcity_in_gb_per_day = var.reservation_capcity_in_gb_per_day
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # retention_in_days - (optional) is a type of number
  retention_in_days = var.retention_in_days
  # sku - (optional) is a type of string
  sku = var.sku
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "id" {
  description = "returns a string"
  value       = azurerm_log_analytics_workspace.this.id
}

output "portal_url" {
  description = "returns a string"
  value       = azurerm_log_analytics_workspace.this.portal_url
}

output "primary_shared_key" {
  description = "returns a string"
  value       = azurerm_log_analytics_workspace.this.primary_shared_key
  sensitive   = true
}

output "retention_in_days" {
  description = "returns a number"
  value       = azurerm_log_analytics_workspace.this.retention_in_days
}

output "secondary_shared_key" {
  description = "returns a string"
  value       = azurerm_log_analytics_workspace.this.secondary_shared_key
  sensitive   = true
}

output "workspace_id" {
  description = "returns a string"
  value       = azurerm_log_analytics_workspace.this.workspace_id
}

output "this" {
  value = azurerm_log_analytics_workspace.this
}
```

[top](#index)