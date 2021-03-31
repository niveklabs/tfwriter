# azurerm_data_factory_trigger_schedule

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
module "azurerm_data_factory_trigger_schedule" {
  source = "./modules/azurerm/r/azurerm_data_factory_trigger_schedule"

  # annotations - (optional) is a type of list of string
  annotations = []
  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # end_time - (optional) is a type of string
  end_time = null
  # frequency - (optional) is a type of string
  frequency = null
  # interval - (optional) is a type of number
  interval = null
  # name - (required) is a type of string
  name = null
  # pipeline_name - (required) is a type of string
  pipeline_name = null
  # pipeline_parameters - (optional) is a type of map of string
  pipeline_parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # start_time - (optional) is a type of string
  start_time = null

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
variable "annotations" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "data_factory_name" {
  description = "(required)"
  type        = string
}

variable "end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pipeline_name" {
  description = "(required)"
  type        = string
}

variable "pipeline_parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "start_time" {
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
resource "azurerm_data_factory_trigger_schedule" "this" {
  annotations         = var.annotations
  data_factory_name   = var.data_factory_name
  end_time            = var.end_time
  frequency           = var.frequency
  interval            = var.interval
  name                = var.name
  pipeline_name       = var.pipeline_name
  pipeline_parameters = var.pipeline_parameters
  resource_group_name = var.resource_group_name
  start_time          = var.start_time

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
  value       = azurerm_data_factory_trigger_schedule.this.id
}

output "start_time" {
  description = "returns a string"
  value       = azurerm_data_factory_trigger_schedule.this.start_time
}

output "this" {
  value = azurerm_data_factory_trigger_schedule.this
}
```

[top](#index)