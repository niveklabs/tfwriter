# azurerm_bot_channels_registration

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
module "azurerm_bot_channels_registration" {
  source = "./modules/azurerm/r/azurerm_bot_channels_registration"

  # developer_app_insights_api_key - (optional) is a type of string
  developer_app_insights_api_key = null
  # developer_app_insights_application_id - (optional) is a type of string
  developer_app_insights_application_id = null
  # developer_app_insights_key - (optional) is a type of string
  developer_app_insights_key = null
  # display_name - (optional) is a type of string
  display_name = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # location - (required) is a type of string
  location = null
  # microsoft_app_id - (required) is a type of string
  microsoft_app_id = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (required) is a type of string
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
variable "developer_app_insights_api_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "developer_app_insights_application_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "developer_app_insights_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "microsoft_app_id" {
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

variable "sku" {
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
resource "azurerm_bot_channels_registration" "this" {
  # developer_app_insights_api_key - (optional) is a type of string
  developer_app_insights_api_key = var.developer_app_insights_api_key
  # developer_app_insights_application_id - (optional) is a type of string
  developer_app_insights_application_id = var.developer_app_insights_application_id
  # developer_app_insights_key - (optional) is a type of string
  developer_app_insights_key = var.developer_app_insights_key
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # endpoint - (optional) is a type of string
  endpoint = var.endpoint
  # location - (required) is a type of string
  location = var.location
  # microsoft_app_id - (required) is a type of string
  microsoft_app_id = var.microsoft_app_id
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku - (required) is a type of string
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
output "developer_app_insights_api_key" {
  description = "returns a string"
  value       = azurerm_bot_channels_registration.this.developer_app_insights_api_key
  sensitive   = true
}

output "developer_app_insights_application_id" {
  description = "returns a string"
  value       = azurerm_bot_channels_registration.this.developer_app_insights_application_id
}

output "developer_app_insights_key" {
  description = "returns a string"
  value       = azurerm_bot_channels_registration.this.developer_app_insights_key
}

output "display_name" {
  description = "returns a string"
  value       = azurerm_bot_channels_registration.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_bot_channels_registration.this.id
}

output "this" {
  value = azurerm_bot_channels_registration.this
}
```

[top](#index)