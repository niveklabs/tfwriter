# fortios_logfortianalyzercloud_setting

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
module "fortios_logfortianalyzercloud_setting" {
  source = "./modules/fortios/r/fortios_logfortianalyzercloud_setting"

  # access_config - (optional) is a type of string
  access_config = null
  # certificate - (optional) is a type of string
  certificate = null
  # conn_timeout - (optional) is a type of number
  conn_timeout = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # hmac_algorithm - (optional) is a type of string
  hmac_algorithm = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # ips_archive - (optional) is a type of string
  ips_archive = null
  # max_log_rate - (optional) is a type of number
  max_log_rate = null
  # monitor_failure_retry_period - (optional) is a type of number
  monitor_failure_retry_period = null
  # monitor_keepalive_period - (optional) is a type of number
  monitor_keepalive_period = null
  # priority - (optional) is a type of string
  priority = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # status - (optional) is a type of string
  status = null
  # upload_day - (optional) is a type of string
  upload_day = null
  # upload_interval - (optional) is a type of string
  upload_interval = null
  # upload_option - (optional) is a type of string
  upload_option = null
  # upload_time - (optional) is a type of string
  upload_time = null
}
```

[top](#index)

### Variables

```terraform
variable "access_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conn_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enc_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hmac_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_archive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_log_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitor_failure_retry_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitor_keepalive_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortianalyzercloud_setting" "this" {
  access_config                = var.access_config
  certificate                  = var.certificate
  conn_timeout                 = var.conn_timeout
  enc_algorithm                = var.enc_algorithm
  hmac_algorithm               = var.hmac_algorithm
  interface                    = var.interface
  interface_select_method      = var.interface_select_method
  ips_archive                  = var.ips_archive
  max_log_rate                 = var.max_log_rate
  monitor_failure_retry_period = var.monitor_failure_retry_period
  monitor_keepalive_period     = var.monitor_keepalive_period
  priority                     = var.priority
  source_ip                    = var.source_ip
  ssl_min_proto_version        = var.ssl_min_proto_version
  status                       = var.status
  upload_day                   = var.upload_day
  upload_interval              = var.upload_interval
  upload_option                = var.upload_option
  upload_time                  = var.upload_time
}
```

[top](#index)

### Outputs

```terraform
output "access_config" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.access_config
}

output "certificate" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.certificate
}

output "conn_timeout" {
  description = "returns a number"
  value       = fortios_logfortianalyzercloud_setting.this.conn_timeout
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.enc_algorithm
}

output "hmac_algorithm" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.hmac_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.interface_select_method
}

output "ips_archive" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.ips_archive
}

output "max_log_rate" {
  description = "returns a number"
  value       = fortios_logfortianalyzercloud_setting.this.max_log_rate
}

output "monitor_failure_retry_period" {
  description = "returns a number"
  value       = fortios_logfortianalyzercloud_setting.this.monitor_failure_retry_period
}

output "monitor_keepalive_period" {
  description = "returns a number"
  value       = fortios_logfortianalyzercloud_setting.this.monitor_keepalive_period
}

output "priority" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.priority
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.status
}

output "upload_day" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.upload_day
}

output "upload_interval" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.upload_interval
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.upload_option
}

output "upload_time" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_setting.this.upload_time
}

output "this" {
  value = fortios_logfortianalyzercloud_setting.this
}
```

[top](#index)