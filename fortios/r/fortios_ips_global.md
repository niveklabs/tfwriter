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
    fortios = ">= 1.11.0"
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
  # ngfw_max_scan_range - (optional) is a type of number
  ngfw_max_scan_range = null
  # packet_log_queue_depth - (optional) is a type of number
  packet_log_queue_depth = null
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

  tls_active_probe = [{
    interface               = null
    interface_select_method = null
    source_ip               = null
    source_ip6              = null
    vdom                    = null
  }]
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

variable "ngfw_max_scan_range" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "packet_log_queue_depth" {
  description = "(optional)"
  type        = number
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

variable "tls_active_probe" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      interface               = string
      interface_select_method = string
      source_ip               = string
      source_ip6              = string
      vdom                    = string
    }
  ))
  default = []
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
  ngfw_max_scan_range        = var.ngfw_max_scan_range
  packet_log_queue_depth     = var.packet_log_queue_depth
  session_limit_mode         = var.session_limit_mode
  skype_client_public_ipaddr = var.skype_client_public_ipaddr
  socket_size                = var.socket_size
  sync_session_ttl           = var.sync_session_ttl
  traffic_submit             = var.traffic_submit

  dynamic "tls_active_probe" {
    for_each = var.tls_active_probe
    content {
      interface               = tls_active_probe.value["interface"]
      interface_select_method = tls_active_probe.value["interface_select_method"]
      source_ip               = tls_active_probe.value["source_ip"]
      source_ip6              = tls_active_probe.value["source_ip6"]
      vdom                    = tls_active_probe.value["vdom"]
    }
  }

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

output "ngfw_max_scan_range" {
  description = "returns a number"
  value       = fortios_ips_global.this.ngfw_max_scan_range
}

output "packet_log_queue_depth" {
  description = "returns a number"
  value       = fortios_ips_global.this.packet_log_queue_depth
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