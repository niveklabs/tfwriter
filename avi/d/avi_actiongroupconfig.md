# avi_actiongroupconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/avi/d/avi_actiongroupconfig"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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

### Datasource

```terraform
data "avi_actiongroupconfig" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "action_script_config_ref" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.action_script_config_ref
}

output "autoscale_trigger_notification" {
  description = "returns a bool"
  value       = data.avi_actiongroupconfig.this.autoscale_trigger_notification
}

output "description" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.description
}

output "email_config_ref" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.email_config_ref
}

output "external_only" {
  description = "returns a bool"
  value       = data.avi_actiongroupconfig.this.external_only
}

output "id" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.id
}

output "level" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.level
}

output "name" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.name
}

output "snmp_trap_profile_ref" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.snmp_trap_profile_ref
}

output "syslog_config_ref" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.syslog_config_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_actiongroupconfig.this.uuid
}

output "this" {
  value = avi_actiongroupconfig.this
}
```

[top](#index)