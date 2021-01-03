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
    datadog = ">= 2.18.1"
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "metric" {
  description = "(required)"
  type        = string
}

variable "per_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "short_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statsd_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unit" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_metric_metadata" "this" {
  description     = var.description
  metric          = var.metric
  per_unit        = var.per_unit
  short_name      = var.short_name
  statsd_interval = var.statsd_interval
  type            = var.type
  unit            = var.unit
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