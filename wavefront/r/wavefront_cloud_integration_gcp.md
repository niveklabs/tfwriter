# wavefront_cloud_integration_gcp

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
module "wavefront_cloud_integration_gcp" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_gcp"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # categories - (optional) is a type of list of string
  categories = []
  # force_save - (optional) is a type of bool
  force_save = null
  # json_key - (required) is a type of string
  json_key = null
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
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

variable "categories" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "force_save" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "json_key" {
  description = "(required)"
  type        = string
}

variable "metric_filter_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
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
resource "wavefront_cloud_integration_gcp" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # categories - (optional) is a type of list of string
  categories = var.categories
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # json_key - (required) is a type of string
  json_key = var.json_key
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = var.metric_filter_regex
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
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
  value       = wavefront_cloud_integration_gcp.this.id
}

output "this" {
  value = wavefront_cloud_integration_gcp.this
}
```

[top](#index)