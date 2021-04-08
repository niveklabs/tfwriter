# wavefront_cloud_integration_cloudtrail

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
module "wavefront_cloud_integration_cloudtrail" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_cloudtrail"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # bucket_name - (required) is a type of string
  bucket_name = null
  # external_id - (required) is a type of string
  external_id = null
  # filter_rule - (optional) is a type of string
  filter_rule = null
  # force_save - (optional) is a type of bool
  force_save = null
  # name - (required) is a type of string
  name = null
  # prefix - (optional) is a type of string
  prefix = null
  # region - (required) is a type of string
  region = null
  # role_arn - (required) is a type of string
  role_arn = null
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

variable "bucket_name" {
  description = "(required)"
  type        = string
}

variable "external_id" {
  description = "(required)"
  type        = string
}

variable "filter_rule" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_cloudtrail" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # bucket_name - (required) is a type of string
  bucket_name = var.bucket_name
  # external_id - (required) is a type of string
  external_id = var.external_id
  # filter_rule - (optional) is a type of string
  filter_rule = var.filter_rule
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # name - (required) is a type of string
  name = var.name
  # prefix - (optional) is a type of string
  prefix = var.prefix
  # region - (required) is a type of string
  region = var.region
  # role_arn - (required) is a type of string
  role_arn = var.role_arn
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
  value       = wavefront_cloud_integration_cloudtrail.this.id
}

output "this" {
  value = wavefront_cloud_integration_cloudtrail.this
}
```

[top](#index)