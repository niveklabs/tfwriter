# datadog_metric_metadata

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_metric_metadata" {
  source = "./modules/datadog/r/datadog_metric_metadata"

  # description - (optional) is a type of string
  description = null
  # metric - (required) is a type of string
  metric = null
  # per_unit - (optional) is a type of string
  per_unit = null
  # short_name - (optional) is a type of string
  short_name = null
  # statsd_interval - (optional) is a type of number
  statsd_interval = null
  # type - (optional) is a type of string
  type = null
  # unit - (optional) is a type of string
  unit = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A description of the metric."
  type        = string
  default     = null
}

variable "metric" {
  description = "(required) - The name of the metric."
  type        = string
}

variable "per_unit" {
  description = "(optional) - Per unit of the metric such as `second` in `bytes per second`."
  type        = string
  default     = null
}

variable "short_name" {
  description = "(optional) - A short name of the metric."
  type        = string
  default     = null
}

variable "statsd_interval" {
  description = "(optional) - If applicable, statsd flush interval in seconds for the metric."
  type        = number
  default     = null
}

variable "type" {
  description = "(optional) - Type of the metric."
  type        = string
  default     = null
}

variable "unit" {
  description = "(optional) - Primary unit of the metric such as `byte` or `operation`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_metric_metadata" "this" {
  # description - (optional) is a type of string
  description = var.description
  # metric - (required) is a type of string
  metric = var.metric
  # per_unit - (optional) is a type of string
  per_unit = var.per_unit
  # short_name - (optional) is a type of string
  short_name = var.short_name
  # statsd_interval - (optional) is a type of number
  statsd_interval = var.statsd_interval
  # type - (optional) is a type of string
  type = var.type
  # unit - (optional) is a type of string
  unit = var.unit
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_metric_metadata.this.id
}

output "this" {
  value = datadog_metric_metadata.this
}
```

[top](#index)