# fortios_logfortianalyzer3_overridesetting

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
module "fortios_logfortianalyzer3_overridesetting" {
  source = "./modules/fortios/r/fortios_logfortianalyzer3_overridesetting"

  # __change_ip - (optional) is a type of number
  __change_ip = null
  # certificate - (optional) is a type of string
  certificate = null
  # conn_timeout - (optional) is a type of number
  conn_timeout = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # faz_type - (optional) is a type of number
  faz_type = null
  # hmac_algorithm - (optional) is a type of string
  hmac_algorithm = null
  # ips_archive - (optional) is a type of string
  ips_archive = null
  # mgmt_name - (optional) is a type of string
  mgmt_name = null
  # monitor_failure_retry_period - (optional) is a type of number
  monitor_failure_retry_period = null
  # monitor_keepalive_period - (optional) is a type of number
  monitor_keepalive_period = null
  # override - (optional) is a type of string
  override = null
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
  # use_management_vdom - (optional) is a type of string
  use_management_vdom = null
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

variable "ips_archive" {
  description = "(optional)"
  type        = string
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

variable "override" {
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

variable "use_management_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortianalyzer3_overridesetting" "this" {
  __change_ip                  = var.__change_ip
  certificate                  = var.certificate
  conn_timeout                 = var.conn_timeout
  enc_algorithm                = var.enc_algorithm
  faz_type                     = var.faz_type
  hmac_algorithm               = var.hmac_algorithm
  ips_archive                  = var.ips_archive
  mgmt_name                    = var.mgmt_name
  monitor_failure_retry_period = var.monitor_failure_retry_period
  monitor_keepalive_period     = var.monitor_keepalive_period
  override                     = var.override
  reliable                     = var.reliable
  server                       = var.server
  source_ip                    = var.source_ip
  ssl_min_proto_version        = var.ssl_min_proto_version
  status                       = var.status
  upload_day                   = var.upload_day
  upload_interval              = var.upload_interval
  upload_option                = var.upload_option
  upload_time                  = var.upload_time
  use_management_vdom          = var.use_management_vdom
}
```

[top](#index)

### Outputs

```terraform
output "__change_ip" {
  description = "returns a number"
  value       = fortios_logfortianalyzer3_overridesetting.this.__change_ip
}

output "certificate" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.certificate
}

output "conn_timeout" {
  description = "returns a number"
  value       = fortios_logfortianalyzer3_overridesetting.this.conn_timeout
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.enc_algorithm
}

output "faz_type" {
  description = "returns a number"
  value       = fortios_logfortianalyzer3_overridesetting.this.faz_type
}

output "hmac_algorithm" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.hmac_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.id
}

output "ips_archive" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.ips_archive
}

output "mgmt_name" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.mgmt_name
}

output "monitor_failure_retry_period" {
  description = "returns a number"
  value       = fortios_logfortianalyzer3_overridesetting.this.monitor_failure_retry_period
}

output "monitor_keepalive_period" {
  description = "returns a number"
  value       = fortios_logfortianalyzer3_overridesetting.this.monitor_keepalive_period
}

output "override" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.override
}

output "reliable" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.reliable
}

output "server" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.status
}

output "upload_day" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.upload_day
}

output "upload_interval" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.upload_interval
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.upload_option
}

output "upload_time" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.upload_time
}

output "use_management_vdom" {
  description = "returns a string"
  value       = fortios_logfortianalyzer3_overridesetting.this.use_management_vdom
}

output "this" {
  value = fortios_logfortianalyzer3_overridesetting.this
}
```

[top](#index)