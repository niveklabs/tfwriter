# azurerm_stream_analytics_job

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
module "azurerm_stream_analytics_job" {
  source = "./modules/azurerm/r/azurerm_stream_analytics_job"

  # compatibility_level - (optional) is a type of string
  compatibility_level = null
  # data_locale - (optional) is a type of string
  data_locale = null
  # events_late_arrival_max_delay_in_seconds - (optional) is a type of number
  events_late_arrival_max_delay_in_seconds = null
  # events_out_of_order_max_delay_in_seconds - (optional) is a type of number
  events_out_of_order_max_delay_in_seconds = null
  # events_out_of_order_policy - (optional) is a type of string
  events_out_of_order_policy = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # output_error_policy - (optional) is a type of string
  output_error_policy = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # streaming_units - (required) is a type of number
  streaming_units = null
  # tags - (optional) is a type of map of string
  tags = {}
  # transformation_query - (required) is a type of string
  transformation_query = null

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
variable "compatibility_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_locale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "events_late_arrival_max_delay_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "events_out_of_order_max_delay_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "events_out_of_order_policy" {
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

variable "output_error_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "streaming_units" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transformation_query" {
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
resource "azurerm_stream_analytics_job" "this" {
  compatibility_level                      = var.compatibility_level
  data_locale                              = var.data_locale
  events_late_arrival_max_delay_in_seconds = var.events_late_arrival_max_delay_in_seconds
  events_out_of_order_max_delay_in_seconds = var.events_out_of_order_max_delay_in_seconds
  events_out_of_order_policy               = var.events_out_of_order_policy
  location                                 = var.location
  name                                     = var.name
  output_error_policy                      = var.output_error_policy
  resource_group_name                      = var.resource_group_name
  streaming_units                          = var.streaming_units
  tags                                     = var.tags
  transformation_query                     = var.transformation_query

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
output "compatibility_level" {
  description = "returns a string"
  value       = azurerm_stream_analytics_job.this.compatibility_level
}

output "data_locale" {
  description = "returns a string"
  value       = azurerm_stream_analytics_job.this.data_locale
}

output "id" {
  description = "returns a string"
  value       = azurerm_stream_analytics_job.this.id
}

output "job_id" {
  description = "returns a string"
  value       = azurerm_stream_analytics_job.this.job_id
}

output "this" {
  value = azurerm_stream_analytics_job.this
}
```

[top](#index)