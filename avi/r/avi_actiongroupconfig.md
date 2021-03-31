# avi_actiongroupconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_actiongroupconfig" {
  source = "./modules/avi/r/avi_actiongroupconfig"

  # action_script_config_ref - (optional) is a type of string
  action_script_config_ref = null
  # autoscale_trigger_notification - (optional) is a type of bool
  autoscale_trigger_notification = null
  # description - (optional) is a type of string
  description = null
  # email_config_ref - (optional) is a type of string
  email_config_ref = null
  # external_only - (required) is a type of bool
  external_only = null
  # level - (required) is a type of string
  level = null
  # name - (required) is a type of string
  name = null
  # snmp_trap_profile_ref - (optional) is a type of string
  snmp_trap_profile_ref = null
  # syslog_config_ref - (optional) is a type of string
  syslog_config_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "action_script_config_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscale_trigger_notification" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_config_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_only" {
  description = "(required)"
  type        = bool
}

variable "level" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "snmp_trap_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syslog_config_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_actiongroupconfig" "this" {
  action_script_config_ref       = var.action_script_config_ref
  autoscale_trigger_notification = var.autoscale_trigger_notification
  description                    = var.description
  email_config_ref               = var.email_config_ref
  external_only                  = var.external_only
  level                          = var.level
  name                           = var.name
  snmp_trap_profile_ref          = var.snmp_trap_profile_ref
  syslog_config_ref              = var.syslog_config_ref
  tenant_ref                     = var.tenant_ref
  uuid                           = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "action_script_config_ref" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.action_script_config_ref
}

output "description" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.description
}

output "email_config_ref" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.email_config_ref
}

output "id" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.id
}

output "snmp_trap_profile_ref" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.snmp_trap_profile_ref
}

output "syslog_config_ref" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.syslog_config_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_actiongroupconfig.this.uuid
}

output "this" {
  value = avi_actiongroupconfig.this
}
```

[top](#index)