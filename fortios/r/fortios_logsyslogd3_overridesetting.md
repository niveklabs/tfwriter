# fortios_logsyslogd3_overridesetting

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
module "fortios_logsyslogd3_overridesetting" {
  source = "./modules/fortios/r/fortios_logsyslogd3_overridesetting"

  # certificate - (optional) is a type of string
  certificate = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # facility - (optional) is a type of string
  facility = null
  # format - (optional) is a type of string
  format = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # max_log_rate - (optional) is a type of number
  max_log_rate = null
  # mode - (optional) is a type of string
  mode = null
  # override - (optional) is a type of string
  override = null
  # port - (optional) is a type of number
  port = null
  # priority - (optional) is a type of string
  priority = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # status - (optional) is a type of string
  status = null
  # syslog_type - (optional) is a type of number
  syslog_type = null

  custom_field_name = [{
    custom = null
    id     = null
    name   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate" {
  description = "(optional)"
  type        = string
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

variable "facility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
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

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority" {
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

variable "syslog_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "custom_field_name" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      custom = string
      id     = number
      name   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logsyslogd3_overridesetting" "this" {
  certificate             = var.certificate
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  enc_algorithm           = var.enc_algorithm
  facility                = var.facility
  format                  = var.format
  interface               = var.interface
  interface_select_method = var.interface_select_method
  max_log_rate            = var.max_log_rate
  mode                    = var.mode
  override                = var.override
  port                    = var.port
  priority                = var.priority
  server                  = var.server
  source_ip               = var.source_ip
  ssl_min_proto_version   = var.ssl_min_proto_version
  status                  = var.status
  syslog_type             = var.syslog_type

  dynamic "custom_field_name" {
    for_each = var.custom_field_name
    content {
      custom = custom_field_name.value["custom"]
      id     = custom_field_name.value["id"]
      name   = custom_field_name.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.certificate
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.enc_algorithm
}

output "facility" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.facility
}

output "format" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.format
}

output "id" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.interface_select_method
}

output "max_log_rate" {
  description = "returns a number"
  value       = fortios_logsyslogd3_overridesetting.this.max_log_rate
}

output "mode" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.mode
}

output "override" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.override
}

output "port" {
  description = "returns a number"
  value       = fortios_logsyslogd3_overridesetting.this.port
}

output "priority" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.priority
}

output "server" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logsyslogd3_overridesetting.this.status
}

output "syslog_type" {
  description = "returns a number"
  value       = fortios_logsyslogd3_overridesetting.this.syslog_type
}

output "this" {
  value = fortios_logsyslogd3_overridesetting.this
}
```

[top](#index)