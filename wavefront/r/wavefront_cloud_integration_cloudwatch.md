# wavefront_cloud_integration_cloudwatch

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
module "wavefront_cloud_integration_cloudwatch" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_cloudwatch"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # external_id - (required) is a type of string
  external_id = null
  # force_save - (optional) is a type of bool
  force_save = null
  # instance_selection_tags - (optional) is a type of map of string
  instance_selection_tags = {}
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = null
  # name - (required) is a type of string
  name = null
  # namespaces - (optional) is a type of list of string
  namespaces = []
  # point_tag_filter_regex - (optional) is a type of string
  point_tag_filter_regex = null
  # role_arn - (required) is a type of string
  role_arn = null
  # service - (optional) is a type of string
  service = null
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = null
  # volume_selection_tags - (optional) is a type of map of string
  volume_selection_tags = {}
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

variable "external_id" {
  description = "(required)"
  type        = string
}

variable "force_save" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_selection_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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

variable "namespaces" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "point_tag_filter_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_arn" {
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

variable "volume_selection_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_cloudwatch" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # external_id - (required) is a type of string
  external_id = var.external_id
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # instance_selection_tags - (optional) is a type of map of string
  instance_selection_tags = var.instance_selection_tags
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = var.metric_filter_regex
  # name - (required) is a type of string
  name = var.name
  # namespaces - (optional) is a type of list of string
  namespaces = var.namespaces
  # point_tag_filter_regex - (optional) is a type of string
  point_tag_filter_regex = var.point_tag_filter_regex
  # role_arn - (required) is a type of string
  role_arn = var.role_arn
  # service - (optional) is a type of string
  service = var.service
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = var.service_refresh_rate_in_minutes
  # volume_selection_tags - (optional) is a type of map of string
  volume_selection_tags = var.volume_selection_tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_cloud_integration_cloudwatch.this.id
}

output "this" {
  value = wavefront_cloud_integration_cloudwatch.this
}
```

[top](#index)