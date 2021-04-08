# wavefront_cloud_integration_azure_activity_log

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
module "wavefront_cloud_integration_azure_activity_log" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_azure_activity_log"

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
  # name - (required) is a type of string
  name = null
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

variable "tenant" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_azure_activity_log" "this" {
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
  # name - (required) is a type of string
  name = var.name
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
  value       = wavefront_cloud_integration_azure_activity_log.this.id
}

output "this" {
  value = wavefront_cloud_integration_azure_activity_log.this
}
```

[top](#index)