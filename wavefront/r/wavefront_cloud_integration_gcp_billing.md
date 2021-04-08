# wavefront_cloud_integration_gcp_billing

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
module "wavefront_cloud_integration_gcp_billing" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_gcp_billing"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # api_key - (required) is a type of string
  api_key = null
  # force_save - (optional) is a type of bool
  force_save = null
  # json_key - (required) is a type of string
  json_key = null
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

variable "api_key" {
  description = "(required)"
  type        = string
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
resource "wavefront_cloud_integration_gcp_billing" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # api_key - (required) is a type of string
  api_key = var.api_key
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # json_key - (required) is a type of string
  json_key = var.json_key
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
  value       = wavefront_cloud_integration_gcp_billing.this.id
}

output "this" {
  value = wavefront_cloud_integration_gcp_billing.this
}
```

[top](#index)