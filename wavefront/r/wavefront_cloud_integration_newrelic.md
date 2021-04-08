# wavefront_cloud_integration_newrelic

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_cloud_integration_newrelic" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_newrelic"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # api_key - (required) is a type of string
  api_key = null
  # app_filter_regex - (optional) is a type of string
  app_filter_regex = null
  # force_save - (optional) is a type of bool
  force_save = null
  # host_filter_regex - (optional) is a type of string
  host_filter_regex = null
  # metric_filter - (optional) is a type of list of object
  metric_filter = [{
    app_name            = null
    metric_filter_regex = null
  }]
  # name - (required) is a type of string
  name = null
  # service - (optional) is a type of string
  service = null
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = null
}
```

[top](#index)

### Variables

```terraform
variable "additional_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "api_key" {
  description = "(required)"
  type        = string
}

variable "app_filter_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_save" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "host_filter_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metric_filter" {
  description = "(optional)"
  type = list(object(
    {
      app_name            = string
      metric_filter_regex = string
    }
  ))
  default = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_refresh_rate_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_newrelic" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # api_key - (required) is a type of string
  api_key = var.api_key
  # app_filter_regex - (optional) is a type of string
  app_filter_regex = var.app_filter_regex
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # host_filter_regex - (optional) is a type of string
  host_filter_regex = var.host_filter_regex
  # metric_filter - (optional) is a type of list of object
  metric_filter = var.metric_filter
  # name - (required) is a type of string
  name = var.name
  # service - (optional) is a type of string
  service = var.service
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = var.service_refresh_rate_in_minutes
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_cloud_integration_newrelic.this.id
}

output "this" {
  value = wavefront_cloud_integration_newrelic.this
}
```

[top](#index)