# azurerm_stream_analytics_job

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_stream_analytics_job" {
  source = "./modules/azurerm/d/azurerm_stream_analytics_job"

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
data "azurerm_stream_analytics_job" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compatibility_level" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.compatibility_level
}

output "data_locale" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.data_locale
}

output "events_late_arrival_max_delay_in_seconds" {
  description = "returns a number"
  value       = data.azurerm_stream_analytics_job.this.events_late_arrival_max_delay_in_seconds
}

output "events_out_of_order_max_delay_in_seconds" {
  description = "returns a number"
  value       = data.azurerm_stream_analytics_job.this.events_out_of_order_max_delay_in_seconds
}

output "events_out_of_order_policy" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.events_out_of_order_policy
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.id
}

output "job_id" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.job_id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.location
}

output "output_error_policy" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.output_error_policy
}

output "streaming_units" {
  description = "returns a number"
  value       = data.azurerm_stream_analytics_job.this.streaming_units
}

output "transformation_query" {
  description = "returns a string"
  value       = data.azurerm_stream_analytics_job.this.transformation_query
}

output "this" {
  value = azurerm_stream_analytics_job.this
}
```

[top](#index)