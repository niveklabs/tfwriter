# fortios_logfortiguard_setting

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
module "fortios_logfortiguard_setting" {
  source = "./modules/fortios/r/fortios_logfortiguard_setting"

  # conn_timeout - (optional) is a type of number
  conn_timeout = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # max_log_rate - (optional) is a type of number
  max_log_rate = null
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

variable "max_log_rate" {
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
resource "fortios_logfortiguard_setting" "this" {
  conn_timeout            = var.conn_timeout
  enc_algorithm           = var.enc_algorithm
  interface               = var.interface
  interface_select_method = var.interface_select_method
  max_log_rate            = var.max_log_rate
  priority                = var.priority
  source_ip               = var.source_ip
  ssl_min_proto_version   = var.ssl_min_proto_version
  status                  = var.status
  upload_day              = var.upload_day
  upload_interval         = var.upload_interval
  upload_option           = var.upload_option
  upload_time             = var.upload_time
}
```

[top](#index)

### Outputs

```terraform
output "conn_timeout" {
  description = "returns a number"
  value       = fortios_logfortiguard_setting.this.conn_timeout
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.enc_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.interface_select_method
}

output "max_log_rate" {
  description = "returns a number"
  value       = fortios_logfortiguard_setting.this.max_log_rate
}

output "priority" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.priority
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.status
}

output "upload_day" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_day
}

output "upload_interval" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_interval
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_option
}

output "upload_time" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_time
}

output "this" {
  value = fortios_logfortiguard_setting.this
}
```

[top](#index)