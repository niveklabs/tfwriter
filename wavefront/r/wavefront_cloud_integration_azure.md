# wavefront_cloud_integration_azure

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
module "wavefront_cloud_integration_azure" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_azure"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # category_filter - (optional) is a type of list of string
  category_filter = []
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # force_save - (optional) is a type of bool
  force_save = null
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = null
  # name - (required) is a type of string
  name = null
  # resource_group_filter - (optional) is a type of list of string
  resource_group_filter = []
  # service - (optional) is a type of string
  service = null
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = null
  # tenant - (required) is a type of string
  tenant = null
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

variable "category_filter" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(required)"
  type        = string
}

variable "force_save" {
  description = "(optional)"
  type        = bool
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

variable "resource_group_filter" {
  description = "(optional)"
  type        = list(string)
  default     = null
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

variable "tenant" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_azure" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # category_filter - (optional) is a type of list of string
  category_filter = var.category_filter
  # client_id - (required) is a type of string
  client_id = var.client_id
  # client_secret - (required) is a type of string
  client_secret = var.client_secret
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = var.metric_filter_regex
  # name - (required) is a type of string
  name = var.name
  # resource_group_filter - (optional) is a type of list of string
  resource_group_filter = var.resource_group_filter
  # service - (optional) is a type of string
  service = var.service
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = var.service_refresh_rate_in_minutes
  # tenant - (required) is a type of string
  tenant = var.tenant
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_cloud_integration_azure.this.id
}

output "this" {
  value = wavefront_cloud_integration_azure.this
}
```

[top](#index)