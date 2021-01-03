# fortios_ips_global

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_ips_global" {
  source = "./modules/fortios/r/fortios_ips_global"

  # anomaly_mode - (optional) is a type of string
  anomaly_mode = null
  # database - (optional) is a type of string
  database = null
  # deep_app_insp_db_limit - (optional) is a type of number
  deep_app_insp_db_limit = null
  # deep_app_insp_timeout - (optional) is a type of number
  deep_app_insp_timeout = null
  # engine_count - (optional) is a type of number
  engine_count = null
  # exclude_signatures - (optional) is a type of string
  exclude_signatures = null
  # fail_open - (optional) is a type of string
  fail_open = null
  # intelligent_mode - (optional) is a type of string
  intelligent_mode = null
  # session_limit_mode - (optional) is a type of string
  session_limit_mode = null
  # skype_client_public_ipaddr - (optional) is a type of string
  skype_client_public_ipaddr = null
  # socket_size - (optional) is a type of number
  socket_size = null
  # sync_session_ttl - (optional) is a type of string
  sync_session_ttl = null
  # traffic_submit - (optional) is a type of string
  traffic_submit = null
}
```

[top](#index)

### Variables

```terraform
variable "anomaly_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deep_app_insp_db_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "deep_app_insp_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "engine_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "exclude_signatures" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fail_open" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intelligent_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_limit_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "skype_client_public_ipaddr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "socket_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sync_session_ttl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_submit" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_global" "this" {
  anomaly_mode               = var.anomaly_mode
  database                   = var.database
  deep_app_insp_db_limit     = var.deep_app_insp_db_limit
  deep_app_insp_timeout      = var.deep_app_insp_timeout
  engine_count               = var.engine_count
  exclude_signatures         = var.exclude_signatures
  fail_open                  = var.fail_open
  intelligent_mode           = var.intelligent_mode
  session_limit_mode         = var.session_limit_mode
  skype_client_public_ipaddr = var.skype_client_public_ipaddr
  socket_size                = var.socket_size
  sync_session_ttl           = var.sync_session_ttl
  traffic_submit             = var.traffic_submit
}
```

[top](#index)

### Outputs

```terraform
output "anomaly_mode" {
  description = "returns a string"
  value       = fortios_ips_global.this.anomaly_mode
}

output "database" {
  description = "returns a string"
  value       = fortios_ips_global.this.database
}

output "deep_app_insp_db_limit" {
  description = "returns a number"
  value       = fortios_ips_global.this.deep_app_insp_db_limit
}

output "deep_app_insp_timeout" {
  description = "returns a number"
  value       = fortios_ips_global.this.deep_app_insp_timeout
}

output "engine_count" {
  description = "returns a number"
  value       = fortios_ips_global.this.engine_count
}

output "exclude_signatures" {
  description = "returns a string"
  value       = fortios_ips_global.this.exclude_signatures
}

output "fail_open" {
  description = "returns a string"
  value       = fortios_ips_global.this.fail_open
}

output "id" {
  description = "returns a string"
  value       = fortios_ips_global.this.id
}

output "intelligent_mode" {
  description = "returns a string"
  value       = fortios_ips_global.this.intelligent_mode
}

output "session_limit_mode" {
  description = "returns a string"
  value       = fortios_ips_global.this.session_limit_mode
}

output "socket_size" {
  description = "returns a number"
  value       = fortios_ips_global.this.socket_size
}

output "sync_session_ttl" {
  description = "returns a string"
  value       = fortios_ips_global.this.sync_session_ttl
}

output "traffic_submit" {
  description = "returns a string"
  value       = fortios_ips_global.this.traffic_submit
}

output "this" {
  value = fortios_ips_global.this
}
```

[top](#index)