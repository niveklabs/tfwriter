# azurerm_iot_time_series_insights_reference_data_set

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
module "azurerm_iot_time_series_insights_reference_data_set" {
  source = "./modules/azurerm/r/azurerm_iot_time_series_insights_reference_data_set"

  # data_string_comparison_behavior - (optional) is a type of string
  data_string_comparison_behavior = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # time_series_insights_environment_id - (required) is a type of string
  time_series_insights_environment_id = null

  key_property = [{
    name = null
    type = null
  }]

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
variable "data_string_comparison_behavior" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "time_series_insights_environment_id" {
  description = "(required)"
  type        = string
}

variable "key_property" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
      type = string
    }
  ))
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
resource "azurerm_iot_time_series_insights_reference_data_set" "this" {
  data_string_comparison_behavior     = var.data_string_comparison_behavior
  location                            = var.location
  name                                = var.name
  tags                                = var.tags
  time_series_insights_environment_id = var.time_series_insights_environment_id

  dynamic "key_property" {
    for_each = var.key_property
    content {
      name = key_property.value["name"]
      type = key_property.value["type"]
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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_iot_time_series_insights_reference_data_set.this.id
}

output "this" {
  value = azurerm_iot_time_series_insights_reference_data_set.this
}
```

[top](#index)