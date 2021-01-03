# fortios_logsyslogd_setting

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
module "fortios_logsyslogd_setting" {
  source = "./modules/fortios/r/fortios_logsyslogd_setting"

  # certificate - (optional) is a type of string
  certificate = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # facility - (optional) is a type of string
  facility = null
  # format - (optional) is a type of string
  format = null
  # mode - (optional) is a type of string
  mode = null
  # port - (optional) is a type of number
  port = null
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

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
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
resource "fortios_logsyslogd_setting" "this" {
  certificate           = var.certificate
  enc_algorithm         = var.enc_algorithm
  facility              = var.facility
  format                = var.format
  mode                  = var.mode
  port                  = var.port
  server                = var.server
  source_ip             = var.source_ip
  ssl_min_proto_version = var.ssl_min_proto_version
  status                = var.status
  syslog_type           = var.syslog_type

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
  value       = fortios_logsyslogd_setting.this.certificate
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.enc_algorithm
}

output "facility" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.facility
}

output "format" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.format
}

output "id" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.mode
}

output "port" {
  description = "returns a number"
  value       = fortios_logsyslogd_setting.this.port
}

output "server" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logsyslogd_setting.this.status
}

output "syslog_type" {
  description = "returns a number"
  value       = fortios_logsyslogd_setting.this.syslog_type
}

output "this" {
  value = fortios_logsyslogd_setting.this
}
```

[top](#index)