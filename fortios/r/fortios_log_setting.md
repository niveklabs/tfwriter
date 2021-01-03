# fortios_log_setting

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
module "fortios_log_setting" {
  source = "./modules/fortios/r/fortios_log_setting"

  # brief_traffic_format - (optional) is a type of string
  brief_traffic_format = null
  # daemon_log - (optional) is a type of string
  daemon_log = null
  # expolicy_implicit_log - (optional) is a type of string
  expolicy_implicit_log = null
  # faz_override - (optional) is a type of string
  faz_override = null
  # fwpolicy6_implicit_log - (optional) is a type of string
  fwpolicy6_implicit_log = null
  # fwpolicy_implicit_log - (optional) is a type of string
  fwpolicy_implicit_log = null
  # local_in_allow - (optional) is a type of string
  local_in_allow = null
  # local_in_deny_broadcast - (optional) is a type of string
  local_in_deny_broadcast = null
  # local_in_deny_unicast - (optional) is a type of string
  local_in_deny_unicast = null
  # local_out - (optional) is a type of string
  local_out = null
  # log_invalid_packet - (optional) is a type of string
  log_invalid_packet = null
  # log_policy_comment - (optional) is a type of string
  log_policy_comment = null
  # log_policy_name - (optional) is a type of string
  log_policy_name = null
  # log_user_in_upper - (optional) is a type of string
  log_user_in_upper = null
  # neighbor_event - (optional) is a type of string
  neighbor_event = null
  # resolve_ip - (optional) is a type of string
  resolve_ip = null
  # resolve_port - (optional) is a type of string
  resolve_port = null
  # syslog_override - (optional) is a type of string
  syslog_override = null
  # user_anonymize - (optional) is a type of string
  user_anonymize = null

  custom_log_fields = [{
    field_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "brief_traffic_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "daemon_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expolicy_implicit_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "faz_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fwpolicy6_implicit_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fwpolicy_implicit_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_in_allow" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_in_deny_broadcast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_in_deny_unicast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_out" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_invalid_packet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_policy_comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_user_in_upper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "neighbor_event" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolve_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolve_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syslog_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_anonymize" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_log_fields" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      field_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_setting" "this" {
  brief_traffic_format    = var.brief_traffic_format
  daemon_log              = var.daemon_log
  expolicy_implicit_log   = var.expolicy_implicit_log
  faz_override            = var.faz_override
  fwpolicy6_implicit_log  = var.fwpolicy6_implicit_log
  fwpolicy_implicit_log   = var.fwpolicy_implicit_log
  local_in_allow          = var.local_in_allow
  local_in_deny_broadcast = var.local_in_deny_broadcast
  local_in_deny_unicast   = var.local_in_deny_unicast
  local_out               = var.local_out
  log_invalid_packet      = var.log_invalid_packet
  log_policy_comment      = var.log_policy_comment
  log_policy_name         = var.log_policy_name
  log_user_in_upper       = var.log_user_in_upper
  neighbor_event          = var.neighbor_event
  resolve_ip              = var.resolve_ip
  resolve_port            = var.resolve_port
  syslog_override         = var.syslog_override
  user_anonymize          = var.user_anonymize

  dynamic "custom_log_fields" {
    for_each = var.custom_log_fields
    content {
      field_id = custom_log_fields.value["field_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "brief_traffic_format" {
  description = "returns a string"
  value       = fortios_log_setting.this.brief_traffic_format
}

output "daemon_log" {
  description = "returns a string"
  value       = fortios_log_setting.this.daemon_log
}

output "expolicy_implicit_log" {
  description = "returns a string"
  value       = fortios_log_setting.this.expolicy_implicit_log
}

output "faz_override" {
  description = "returns a string"
  value       = fortios_log_setting.this.faz_override
}

output "fwpolicy6_implicit_log" {
  description = "returns a string"
  value       = fortios_log_setting.this.fwpolicy6_implicit_log
}

output "fwpolicy_implicit_log" {
  description = "returns a string"
  value       = fortios_log_setting.this.fwpolicy_implicit_log
}

output "id" {
  description = "returns a string"
  value       = fortios_log_setting.this.id
}

output "local_in_allow" {
  description = "returns a string"
  value       = fortios_log_setting.this.local_in_allow
}

output "local_in_deny_broadcast" {
  description = "returns a string"
  value       = fortios_log_setting.this.local_in_deny_broadcast
}

output "local_in_deny_unicast" {
  description = "returns a string"
  value       = fortios_log_setting.this.local_in_deny_unicast
}

output "local_out" {
  description = "returns a string"
  value       = fortios_log_setting.this.local_out
}

output "log_invalid_packet" {
  description = "returns a string"
  value       = fortios_log_setting.this.log_invalid_packet
}

output "log_policy_comment" {
  description = "returns a string"
  value       = fortios_log_setting.this.log_policy_comment
}

output "log_policy_name" {
  description = "returns a string"
  value       = fortios_log_setting.this.log_policy_name
}

output "log_user_in_upper" {
  description = "returns a string"
  value       = fortios_log_setting.this.log_user_in_upper
}

output "neighbor_event" {
  description = "returns a string"
  value       = fortios_log_setting.this.neighbor_event
}

output "resolve_ip" {
  description = "returns a string"
  value       = fortios_log_setting.this.resolve_ip
}

output "resolve_port" {
  description = "returns a string"
  value       = fortios_log_setting.this.resolve_port
}

output "syslog_override" {
  description = "returns a string"
  value       = fortios_log_setting.this.syslog_override
}

output "user_anonymize" {
  description = "returns a string"
  value       = fortios_log_setting.this.user_anonymize
}

output "this" {
  value = fortios_log_setting.this
}
```

[top](#index)