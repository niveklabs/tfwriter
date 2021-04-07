# fortios_logfortianalyzer2_setting

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
module "fortios_logfortianalyzer2_setting" {
  source = "./modules/fortios/r/fortios_logfortianalyzer2_setting"

  # __change_ip - (optional) is a type of number
  __change_ip = null
  # access_config - (optional) is a type of string
  access_config = null
  # certificate - (optional) is a type of string
  certificate = null
  # certificate_verification - (optional) is a type of string
  certificate_verification = null
  # conn_timeout - (optional) is a type of number
  conn_timeout = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # faz_type - (optional) is a type of number
  faz_type = null
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
  # mgmt_name - (optional) is a type of string
  mgmt_name = null
  # monitor_failure_retry_period - (optional) is a type of number
  monitor_failure_retry_period = null
  # monitor_keepalive_period - (optional) is a type of number
  monitor_keepalive_period = null
  # priority - (optional) is a type of string
  priority = null
  # reliable - (optional) is a type of string
  reliable = null
  # server - (optional) is a type of string
  server = null
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

  serial = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "__change_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

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

variable "certificate_verification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conn_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enc_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "faz_type" {
  description = "(optional)"
  type        = number
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

variable "mgmt_name" {
  description = "(optional)"
  type        = string
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

variable "reliable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
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

variable "serial" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortianalyzer2_setting" "this" {
  # __change_ip - (optional) is a type of number
  __change_ip = var.__change_ip
  # access_config - (optional) is a type of string
  access_config = var.access_config
  # certificate - (optional) is a type of string
  certificate = var.certificate
  # certificate_verification - (optional) is a type of string
  certificate_verification = var.certificate_verification
  # conn_timeout - (optional) is a type of number
  conn_timeout = var.conn_timeout
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = var.enc_algorithm
  # faz_type - (optional) is a type of number
  faz_type = var.faz_type
  # hmac_algorithm - (optional) is a type of string
  hmac_algorithm = var.hmac_algorithm
  # interface - (optional) is a type of string
  interface = var.interface
  # interface_select_method - (optional) is a type of string
  interface_select_method = var.interface_select_method
  # ips_archive - (optional) is a type of string
  ips_archive = var.ips_archive
  # max_log_rate - (optional) is a type of number
  max_log_rate = var.max_log_rate
  # mgmt_name - (optional) is a type of string
  mgmt_name = var.mgmt_name
  # monitor_failure_retry_period - (optional) is a type of number
  monitor_failure_retry_period = var.monitor_failure_retry_period
  # monitor_keepalive_period - (optional) is a type of number
  monitor_keepalive_period = var.monitor_keepalive_period
  # priority - (optional) is a type of string
  priority = var.priority
  # reliable - (optional) is a type of string
  reliable = var.reliable
  # server - (optional) is a type of string
  server = var.server
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = var.ssl_min_proto_version
  # status - (optional) is a type of string
  status = var.status
  # upload_day - (optional) is a type of string
  upload_day = var.upload_day
  # upload_interval - (optional) is a type of string
  upload_interval = var.upload_interval
  # upload_option - (optional) is a type of string
  upload_option = var.upload_option
  # upload_time - (optional) is a type of string
  upload_time = var.upload_time

  dynamic "serial" {
    for_each = var.serial
    content {
      # name - (optional) is a type of string
      name = serial.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "__change_ip" {
  description = "returns a number"
  value       = fortios_logfortianalyzer2_setting.this.__change_ip
}

output "access_config" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.access_config
}

output "certificate" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.certificate
}

output "certificate_verification" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.certificate_verification
}

output "conn_timeout" {
  description = "returns a number"
  value       = fortios_logfortianalyzer2_setting.this.conn_timeout
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.enc_algorithm
}

output "faz_type" {
  description = "returns a number"
  value       = fortios_logfortianalyzer2_setting.this.faz_type
}

output "hmac_algorithm" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.hmac_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.interface_select_method
}

output "ips_archive" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.ips_archive
}

output "max_log_rate" {
  description = "returns a number"
  value       = fortios_logfortianalyzer2_setting.this.max_log_rate
}

output "mgmt_name" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.mgmt_name
}

output "monitor_failure_retry_period" {
  description = "returns a number"
  value       = fortios_logfortianalyzer2_setting.this.monitor_failure_retry_period
}

output "monitor_keepalive_period" {
  description = "returns a number"
  value       = fortios_logfortianalyzer2_setting.this.monitor_keepalive_period
}

output "priority" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.priority
}

output "reliable" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.reliable
}

output "server" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.status
}

output "upload_day" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.upload_day
}

output "upload_interval" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.upload_interval
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.upload_option
}

output "upload_time" {
  description = "returns a string"
  value       = fortios_logfortianalyzer2_setting.this.upload_time
}

output "this" {
  value = fortios_logfortianalyzer2_setting.this
}
```

[top](#index)