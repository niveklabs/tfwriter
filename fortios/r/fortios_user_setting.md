# fortios_user_setting

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_setting" {
  source = "./modules/fortios/r/fortios_user_setting"

  # auth_blackout_time - (optional) is a type of number
  auth_blackout_time = null
  # auth_ca_cert - (optional) is a type of string
  auth_ca_cert = null
  # auth_cert - (optional) is a type of string
  auth_cert = null
  # auth_http_basic - (optional) is a type of string
  auth_http_basic = null
  # auth_invalid_max - (optional) is a type of number
  auth_invalid_max = null
  # auth_lockout_duration - (optional) is a type of number
  auth_lockout_duration = null
  # auth_lockout_threshold - (optional) is a type of number
  auth_lockout_threshold = null
  # auth_on_demand - (optional) is a type of string
  auth_on_demand = null
  # auth_portal_timeout - (optional) is a type of number
  auth_portal_timeout = null
  # auth_secure_http - (optional) is a type of string
  auth_secure_http = null
  # auth_src_mac - (optional) is a type of string
  auth_src_mac = null
  # auth_ssl_allow_renegotiation - (optional) is a type of string
  auth_ssl_allow_renegotiation = null
  # auth_ssl_min_proto_version - (optional) is a type of string
  auth_ssl_min_proto_version = null
  # auth_timeout - (optional) is a type of number
  auth_timeout = null
  # auth_timeout_type - (optional) is a type of string
  auth_timeout_type = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # per_policy_disclaimer - (optional) is a type of string
  per_policy_disclaimer = null
  # radius_ses_timeout_act - (optional) is a type of string
  radius_ses_timeout_act = null

  auth_ports = [{
    id   = null
    port = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_blackout_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_http_basic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_invalid_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_lockout_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_lockout_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_on_demand" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_portal_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_secure_http" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_src_mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_ssl_allow_renegotiation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_timeout_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_policy_disclaimer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_ses_timeout_act" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_ports" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = number
      port = number
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_setting" "this" {
  auth_blackout_time           = var.auth_blackout_time
  auth_ca_cert                 = var.auth_ca_cert
  auth_cert                    = var.auth_cert
  auth_http_basic              = var.auth_http_basic
  auth_invalid_max             = var.auth_invalid_max
  auth_lockout_duration        = var.auth_lockout_duration
  auth_lockout_threshold       = var.auth_lockout_threshold
  auth_on_demand               = var.auth_on_demand
  auth_portal_timeout          = var.auth_portal_timeout
  auth_secure_http             = var.auth_secure_http
  auth_src_mac                 = var.auth_src_mac
  auth_ssl_allow_renegotiation = var.auth_ssl_allow_renegotiation
  auth_ssl_min_proto_version   = var.auth_ssl_min_proto_version
  auth_timeout                 = var.auth_timeout
  auth_timeout_type            = var.auth_timeout_type
  auth_type                    = var.auth_type
  dynamic_sort_subtable        = var.dynamic_sort_subtable
  per_policy_disclaimer        = var.per_policy_disclaimer
  radius_ses_timeout_act       = var.radius_ses_timeout_act

  dynamic "auth_ports" {
    for_each = var.auth_ports
    content {
      id   = auth_ports.value["id"]
      port = auth_ports.value["port"]
      type = auth_ports.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_blackout_time" {
  description = "returns a number"
  value       = fortios_user_setting.this.auth_blackout_time
}

output "auth_ca_cert" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_ca_cert
}

output "auth_cert" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_cert
}

output "auth_http_basic" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_http_basic
}

output "auth_invalid_max" {
  description = "returns a number"
  value       = fortios_user_setting.this.auth_invalid_max
}

output "auth_lockout_duration" {
  description = "returns a number"
  value       = fortios_user_setting.this.auth_lockout_duration
}

output "auth_lockout_threshold" {
  description = "returns a number"
  value       = fortios_user_setting.this.auth_lockout_threshold
}

output "auth_on_demand" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_on_demand
}

output "auth_portal_timeout" {
  description = "returns a number"
  value       = fortios_user_setting.this.auth_portal_timeout
}

output "auth_secure_http" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_secure_http
}

output "auth_src_mac" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_src_mac
}

output "auth_ssl_allow_renegotiation" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_ssl_allow_renegotiation
}

output "auth_ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_ssl_min_proto_version
}

output "auth_timeout" {
  description = "returns a number"
  value       = fortios_user_setting.this.auth_timeout
}

output "auth_timeout_type" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_timeout_type
}

output "auth_type" {
  description = "returns a string"
  value       = fortios_user_setting.this.auth_type
}

output "id" {
  description = "returns a string"
  value       = fortios_user_setting.this.id
}

output "per_policy_disclaimer" {
  description = "returns a string"
  value       = fortios_user_setting.this.per_policy_disclaimer
}

output "radius_ses_timeout_act" {
  description = "returns a string"
  value       = fortios_user_setting.this.radius_ses_timeout_act
}

output "this" {
  value = fortios_user_setting.this
}
```

[top](#index)