# wavefront_cloud_integration_app_dynamics

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
module "wavefront_cloud_integration_app_dynamics" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_app_dynamics"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # app_filter_regex - (optional) is a type of list of string
  app_filter_regex = []
  # controller_name - (required) is a type of string
  controller_name = null
  # enable_app_infra_metrics - (optional) is a type of bool
  enable_app_infra_metrics = null
  # enable_backend_metrics - (optional) is a type of bool
  enable_backend_metrics = null
  # enable_business_trx_metrics - (optional) is a type of bool
  enable_business_trx_metrics = null
  # enable_error_metrics - (optional) is a type of bool
  enable_error_metrics = null
  # enable_individual_node_metrics - (optional) is a type of bool
  enable_individual_node_metrics = null
  # enable_overall_perf_metrics - (optional) is a type of bool
  enable_overall_perf_metrics = null
  # enable_rollup - (optional) is a type of bool
  enable_rollup = null
  # enable_service_endpoint_metrics - (optional) is a type of bool
  enable_service_endpoint_metrics = null
  # encrypted_password - (required) is a type of string
  encrypted_password = null
  # force_save - (optional) is a type of bool
  force_save = null
  # name - (required) is a type of string
  name = null
  # service - (optional) is a type of string
  service = null
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = null
  # user_name - (required) is a type of string
  user_name = null
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

variable "app_filter_regex" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "controller_name" {
  description = "(required)"
  type        = string
}

variable "enable_app_infra_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_backend_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_business_trx_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_error_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_individual_node_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_overall_perf_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_rollup" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_service_endpoint_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "encrypted_password" {
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

variable "user_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_app_dynamics" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # app_filter_regex - (optional) is a type of list of string
  app_filter_regex = var.app_filter_regex
  # controller_name - (required) is a type of string
  controller_name = var.controller_name
  # enable_app_infra_metrics - (optional) is a type of bool
  enable_app_infra_metrics = var.enable_app_infra_metrics
  # enable_backend_metrics - (optional) is a type of bool
  enable_backend_metrics = var.enable_backend_metrics
  # enable_business_trx_metrics - (optional) is a type of bool
  enable_business_trx_metrics = var.enable_business_trx_metrics
  # enable_error_metrics - (optional) is a type of bool
  enable_error_metrics = var.enable_error_metrics
  # enable_individual_node_metrics - (optional) is a type of bool
  enable_individual_node_metrics = var.enable_individual_node_metrics
  # enable_overall_perf_metrics - (optional) is a type of bool
  enable_overall_perf_metrics = var.enable_overall_perf_metrics
  # enable_rollup - (optional) is a type of bool
  enable_rollup = var.enable_rollup
  # enable_service_endpoint_metrics - (optional) is a type of bool
  enable_service_endpoint_metrics = var.enable_service_endpoint_metrics
  # encrypted_password - (required) is a type of string
  encrypted_password = var.encrypted_password
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # name - (required) is a type of string
  name = var.name
  # service - (optional) is a type of string
  service = var.service
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = var.service_refresh_rate_in_minutes
  # user_name - (required) is a type of string
  user_name = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_cloud_integration_app_dynamics.this.id
}

output "this" {
  value = wavefront_cloud_integration_app_dynamics.this
}
```

[top](#index)