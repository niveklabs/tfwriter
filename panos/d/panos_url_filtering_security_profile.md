# panos_url_filtering_security_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_url_filtering_security_profile" {
  source = "./modules/panos/d/panos_url_filtering_security_profile"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_url_filtering_security_profile" "this" {
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "alert_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.alert_categories
}

output "allow_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.allow_categories
}

output "allow_list" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.allow_list
}

output "block_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.block_categories
}

output "block_list" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.block_list
}

output "block_list_action" {
  description = "returns a string"
  value       = data.panos_url_filtering_security_profile.this.block_list_action
}

output "continue_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.continue_categories
}

output "description" {
  description = "returns a string"
  value       = data.panos_url_filtering_security_profile.this.description
}

output "dynamic_url" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.dynamic_url
}

output "expired_license_action" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.expired_license_action
}

output "http_header_insertion" {
  description = "returns a list of object"
  value       = data.panos_url_filtering_security_profile.this.http_header_insertion
}

output "id" {
  description = "returns a string"
  value       = data.panos_url_filtering_security_profile.this.id
}

output "log_container_page_only" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.log_container_page_only
}

output "log_http_header_referer" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.log_http_header_referer
}

output "log_http_header_user_agent" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.log_http_header_user_agent
}

output "log_http_header_xff" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.log_http_header_xff
}

output "machine_learning_exceptions" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.machine_learning_exceptions
}

output "machine_learning_model" {
  description = "returns a list of object"
  value       = data.panos_url_filtering_security_profile.this.machine_learning_model
}

output "override_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.override_categories
}

output "safe_search_enforcement" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.safe_search_enforcement
}

output "track_container_page" {
  description = "returns a bool"
  value       = data.panos_url_filtering_security_profile.this.track_container_page
}

output "ucd_alert_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.ucd_alert_categories
}

output "ucd_allow_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.ucd_allow_categories
}

output "ucd_block_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.ucd_block_categories
}

output "ucd_continue_categories" {
  description = "returns a list of string"
  value       = data.panos_url_filtering_security_profile.this.ucd_continue_categories
}

output "ucd_log_severity" {
  description = "returns a string"
  value       = data.panos_url_filtering_security_profile.this.ucd_log_severity
}

output "ucd_mode" {
  description = "returns a string"
  value       = data.panos_url_filtering_security_profile.this.ucd_mode
}

output "ucd_mode_group_mapping" {
  description = "returns a string"
  value       = data.panos_url_filtering_security_profile.this.ucd_mode_group_mapping
}

output "this" {
  value = panos_url_filtering_security_profile.this
}
```

[top](#index)