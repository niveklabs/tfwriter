# alicloud_waf_instance

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_waf_instance" {
  source = "./modules/alicloud/r/alicloud_waf_instance"

  # big_screen - (required) is a type of string
  big_screen = null
  # exclusive_ip_package - (required) is a type of string
  exclusive_ip_package = null
  # ext_bandwidth - (required) is a type of string
  ext_bandwidth = null
  # ext_domain_package - (required) is a type of string
  ext_domain_package = null
  # log_storage - (required) is a type of string
  log_storage = null
  # log_time - (required) is a type of string
  log_time = null
  # modify_type - (optional) is a type of string
  modify_type = null
  # package_code - (required) is a type of string
  package_code = null
  # period - (optional) is a type of number
  period = null
  # prefessional_service - (required) is a type of string
  prefessional_service = null
  # renew_period - (optional) is a type of number
  renew_period = null
  # renewal_status - (optional) is a type of string
  renewal_status = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # subscription_type - (required) is a type of string
  subscription_type = null
  # waf_log - (required) is a type of string
  waf_log = null
}
```

[top](#index)

### Variables

```terraform
variable "big_screen" {
  description = "(required)"
  type        = string
}

variable "exclusive_ip_package" {
  description = "(required)"
  type        = string
}

variable "ext_bandwidth" {
  description = "(required)"
  type        = string
}

variable "ext_domain_package" {
  description = "(required)"
  type        = string
}

variable "log_storage" {
  description = "(required)"
  type        = string
}

variable "log_time" {
  description = "(required)"
  type        = string
}

variable "modify_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_code" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "prefessional_service" {
  description = "(required)"
  type        = string
}

variable "renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "renewal_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_type" {
  description = "(required)"
  type        = string
}

variable "waf_log" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_waf_instance" "this" {
  big_screen           = var.big_screen
  exclusive_ip_package = var.exclusive_ip_package
  ext_bandwidth        = var.ext_bandwidth
  ext_domain_package   = var.ext_domain_package
  log_storage          = var.log_storage
  log_time             = var.log_time
  modify_type          = var.modify_type
  package_code         = var.package_code
  period               = var.period
  prefessional_service = var.prefessional_service
  renew_period         = var.renew_period
  renewal_status       = var.renewal_status
  resource_group_id    = var.resource_group_id
  subscription_type    = var.subscription_type
  waf_log              = var.waf_log
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_waf_instance.this.id
}

output "status" {
  description = "returns a number"
  value       = alicloud_waf_instance.this.status
}

output "this" {
  value = alicloud_waf_instance.this
}
```

[top](#index)