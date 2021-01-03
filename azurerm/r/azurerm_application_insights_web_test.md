# azurerm_application_insights_web_test

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
module "azurerm_application_insights_web_test" {
  source = "./modules/azurerm/r/azurerm_application_insights_web_test"

  # application_insights_id - (required) is a type of string
  application_insights_id = null
  # configuration - (required) is a type of string
  configuration = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # frequency - (optional) is a type of number
  frequency = null
  # geo_locations - (required) is a type of list of string
  geo_locations = []
  # kind - (required) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # retry_enabled - (optional) is a type of bool
  retry_enabled = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timeout - (optional) is a type of number
  timeout = null

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
variable "application_insights_id" {
  description = "(required)"
  type        = string
}

variable "configuration" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "frequency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "geo_locations" {
  description = "(required)"
  type        = list(string)
}

variable "kind" {
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

variable "retry_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeout" {
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
resource "azurerm_application_insights_web_test" "this" {
  application_insights_id = var.application_insights_id
  configuration           = var.configuration
  description             = var.description
  enabled                 = var.enabled
  frequency               = var.frequency
  geo_locations           = var.geo_locations
  kind                    = var.kind
  location                = var.location
  name                    = var.name
  resource_group_name     = var.resource_group_name
  retry_enabled           = var.retry_enabled
  tags                    = var.tags
  timeout                 = var.timeout

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
  value       = azurerm_application_insights_web_test.this.id
}

output "synthetic_monitor_id" {
  description = "returns a string"
  value       = azurerm_application_insights_web_test.this.synthetic_monitor_id
}

output "this" {
  value = azurerm_application_insights_web_test.this
}
```

[top](#index)