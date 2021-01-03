# akamai_gtm_domain

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_gtm_domain" {
  source = "./modules/akamai/r/akamai_gtm_domain"

  # cname_coalescing_enabled - (optional) is a type of bool
  cname_coalescing_enabled = null
  # comment - (optional) is a type of string
  comment = null
  # contract - (optional) is a type of string
  contract = null
  # default_error_penalty - (optional) is a type of number
  default_error_penalty = null
  # default_ssl_client_certificate - (optional) is a type of string
  default_ssl_client_certificate = null
  # default_ssl_client_private_key - (optional) is a type of string
  default_ssl_client_private_key = null
  # default_timeout_penalty - (optional) is a type of number
  default_timeout_penalty = null
  # email_notification_list - (optional) is a type of list of string
  email_notification_list = []
  # end_user_mapping_enabled - (optional) is a type of bool
  end_user_mapping_enabled = null
  # group - (optional) is a type of string
  group = null
  # load_feedback - (optional) is a type of bool
  load_feedback = null
  # load_imbalance_percentage - (optional) is a type of number
  load_imbalance_percentage = null
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = null
}
```

[top](#index)

### Variables

```terraform
variable "cname_coalescing_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_error_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_ssl_client_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_ssl_client_private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_timeout_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "email_notification_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "end_user_mapping_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_feedback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_imbalance_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "wait_on_complete" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "akamai_gtm_domain" "this" {
  cname_coalescing_enabled       = var.cname_coalescing_enabled
  comment                        = var.comment
  contract                       = var.contract
  default_error_penalty          = var.default_error_penalty
  default_ssl_client_certificate = var.default_ssl_client_certificate
  default_ssl_client_private_key = var.default_ssl_client_private_key
  default_timeout_penalty        = var.default_timeout_penalty
  email_notification_list        = var.email_notification_list
  end_user_mapping_enabled       = var.end_user_mapping_enabled
  group                          = var.group
  load_feedback                  = var.load_feedback
  load_imbalance_percentage      = var.load_imbalance_percentage
  name                           = var.name
  type                           = var.type
  wait_on_complete               = var.wait_on_complete
}
```

[top](#index)

### Outputs

```terraform
output "default_health_max" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.default_health_max
}

output "default_health_multiplier" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.default_health_multiplier
}

output "default_health_threshold" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.default_health_threshold
}

output "default_max_unreachable_penalty" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.default_max_unreachable_penalty
}

output "default_unreachable_threshold" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.default_unreachable_threshold
}

output "id" {
  description = "returns a string"
  value       = akamai_gtm_domain.this.id
}

output "map_update_interval" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.map_update_interval
}

output "max_properties" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.max_properties
}

output "max_resources" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.max_resources
}

output "max_test_timeout" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.max_test_timeout
}

output "max_ttl" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.max_ttl
}

output "min_pingable_region_fraction" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.min_pingable_region_fraction
}

output "min_test_interval" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.min_test_interval
}

output "min_ttl" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.min_ttl
}

output "ping_interval" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.ping_interval
}

output "ping_packet_size" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.ping_packet_size
}

output "round_robin_prefix" {
  description = "returns a string"
  value       = akamai_gtm_domain.this.round_robin_prefix
}

output "servermonitor_liveness_count" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.servermonitor_liveness_count
}

output "servermonitor_load_count" {
  description = "returns a number"
  value       = akamai_gtm_domain.this.servermonitor_load_count
}

output "servermonitor_pool" {
  description = "returns a string"
  value       = akamai_gtm_domain.this.servermonitor_pool
}

output "this" {
  value = akamai_gtm_domain.this
}
```

[top](#index)