# datadog_metric_tag_configuration

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
module "datadog_metric_tag_configuration" {
  source = "./modules/datadog/r/datadog_metric_tag_configuration"

  # include_percentiles - (optional) is a type of bool
  include_percentiles = null
  # metric_name - (required) is a type of string
  metric_name = null
  # metric_type - (required) is a type of string
  metric_type = null
  # tags - (required) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "include_percentiles" {
  description = "(optional) - Toggle to include/exclude percentiles for a distribution metric. Defaults to false. Can only be applied to metrics that have a metric_type of distribution."
  type        = bool
  default     = null
}

variable "metric_name" {
  description = "(required) - The metric name for this resource."
  type        = string
}

variable "metric_type" {
  description = "(required) - The metric's type. This field can't be updated after creation. Allowed enum values: gauge,count,distribution."
  type        = string
}

variable "tags" {
  description = "(required) - A list of tag keys that will be queryable for your metric."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "datadog_metric_tag_configuration" "this" {
  include_percentiles = var.include_percentiles
  metric_name         = var.metric_name
  metric_type         = var.metric_type
  tags                = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_metric_tag_configuration.this.id
}

output "this" {
  value = datadog_metric_tag_configuration.this
}
```

[top](#index)