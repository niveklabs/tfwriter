# oci_metering_computation_usage

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_metering_computation_usage" {
  source = "./modules/oci/r/oci_metering_computation_usage"

  # compartment_depth - (optional) is a type of number
  compartment_depth = null
  # filter - (optional) is a type of string
  filter = null
  # granularity - (required) is a type of string
  granularity = null
  # group_by - (optional) is a type of list of string
  group_by = []
  # is_aggregate_by_time - (optional) is a type of bool
  is_aggregate_by_time = null
  # query_type - (optional) is a type of string
  query_type = null
  # tenant_id - (required) is a type of string
  tenant_id = null
  # time_usage_ended - (required) is a type of string
  time_usage_ended = null
  # time_usage_started - (required) is a type of string
  time_usage_started = null

  forecast = [{
    forecast_type         = null
    time_forecast_ended   = null
    time_forecast_started = null
  }]

  group_by_tag = [{
    key       = null
    namespace = null
    value     = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_depth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "granularity" {
  description = "(required)"
  type        = string
}

variable "group_by" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "is_aggregate_by_time" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "query_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "time_usage_ended" {
  description = "(required)"
  type        = string
}

variable "time_usage_started" {
  description = "(required)"
  type        = string
}

variable "forecast" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      forecast_type         = string
      time_forecast_ended   = string
      time_forecast_started = string
    }
  ))
  default = []
}

variable "group_by_tag" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key       = string
      namespace = string
      value     = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_metering_computation_usage" "this" {
  compartment_depth    = var.compartment_depth
  filter               = var.filter
  granularity          = var.granularity
  group_by             = var.group_by
  is_aggregate_by_time = var.is_aggregate_by_time
  query_type           = var.query_type
  tenant_id            = var.tenant_id
  time_usage_ended     = var.time_usage_ended
  time_usage_started   = var.time_usage_started

  dynamic "forecast" {
    for_each = var.forecast
    content {
      forecast_type         = forecast.value["forecast_type"]
      time_forecast_ended   = forecast.value["time_forecast_ended"]
      time_forecast_started = forecast.value["time_forecast_started"]
    }
  }

  dynamic "group_by_tag" {
    for_each = var.group_by_tag
    content {
      key       = group_by_tag.value["key"]
      namespace = group_by_tag.value["namespace"]
      value     = group_by_tag.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_depth" {
  description = "returns a number"
  value       = oci_metering_computation_usage.this.compartment_depth
}

output "group_by" {
  description = "returns a list of string"
  value       = oci_metering_computation_usage.this.group_by
}

output "id" {
  description = "returns a string"
  value       = oci_metering_computation_usage.this.id
}

output "is_aggregate_by_time" {
  description = "returns a bool"
  value       = oci_metering_computation_usage.this.is_aggregate_by_time
}

output "items" {
  description = "returns a list of object"
  value       = oci_metering_computation_usage.this.items
}

output "query_type" {
  description = "returns a string"
  value       = oci_metering_computation_usage.this.query_type
}

output "this" {
  value = oci_metering_computation_usage.this
}
```

[top](#index)