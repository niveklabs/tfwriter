# azurerm_monitor_scheduled_query_rules_log

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
module "azurerm_monitor_scheduled_query_rules_log" {
  source = "./modules/azurerm/r/azurerm_monitor_scheduled_query_rules_log"

  # authorized_resource_ids - (optional) is a type of set of string
  authorized_resource_ids = []
  # data_source_id - (required) is a type of string
  data_source_id = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  criteria = [{
    dimension = [{
      name     = null
      operator = null
      values   = []
    }]
    metric_name = null
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
variable "authorized_resource_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "data_source_id" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "criteria" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      dimension = set(object(
        {
          name     = string
          operator = string
          values   = list(string)
        }
      ))
      metric_name = string
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
resource "azurerm_monitor_scheduled_query_rules_log" "this" {
  # authorized_resource_ids - (optional) is a type of set of string
  authorized_resource_ids = var.authorized_resource_ids
  # data_source_id - (required) is a type of string
  data_source_id = var.data_source_id
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "criteria" {
    for_each = var.criteria
    content {
      # metric_name - (required) is a type of string
      metric_name = criteria.value["metric_name"]

      dynamic "dimension" {
        for_each = criteria.value.dimension
        content {
          # name - (required) is a type of string
          name = dimension.value["name"]
          # operator - (optional) is a type of string
          operator = dimension.value["operator"]
          # values - (required) is a type of list of string
          values = dimension.value["values"]
        }
      }

    }
  }

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
  value       = azurerm_monitor_scheduled_query_rules_log.this.id
}

output "this" {
  value = azurerm_monitor_scheduled_query_rules_log.this
}
```

[top](#index)