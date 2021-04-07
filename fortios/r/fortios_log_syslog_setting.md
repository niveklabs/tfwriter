# fortios_log_syslog_setting

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
module "fortios_log_syslog_setting" {
  source = "./modules/fortios/r/fortios_log_syslog_setting"

  # facility - (optional) is a type of string
  facility = null
  # format - (optional) is a type of string
  format = null
  # mode - (optional) is a type of string
  mode = null
  # port - (optional) is a type of string
  port = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # status - (required) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
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

variable "status" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_syslog_setting" "this" {
  # facility - (optional) is a type of string
  facility = var.facility
  # format - (optional) is a type of string
  format = var.format
  # mode - (optional) is a type of string
  mode = var.mode
  # port - (optional) is a type of string
  port = var.port
  # server - (optional) is a type of string
  server = var.server
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # status - (required) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "facility" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.facility
}

output "format" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.format
}

output "id" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.mode
}

output "port" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.port
}

output "server" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_log_syslog_setting.this.source_ip
}

output "this" {
  value = fortios_log_syslog_setting.this
}
```

[top](#index)