# avi_scheduler

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
module "avi_scheduler" {
  source = "./modules/avi/r/avi_scheduler"

  # backup_config_ref - (optional) is a type of string
  backup_config_ref = null
  # enabled - (optional) is a type of bool
  enabled = null
  # end_date_time - (optional) is a type of string
  end_date_time = null
  # frequency - (optional) is a type of number
  frequency = null
  # frequency_unit - (optional) is a type of string
  frequency_unit = null
  # name - (required) is a type of string
  name = null
  # run_mode - (optional) is a type of string
  run_mode = null
  # run_script_ref - (optional) is a type of string
  run_script_ref = null
  # scheduler_action - (optional) is a type of string
  scheduler_action = null
  # start_date_time - (optional) is a type of string
  start_date_time = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_config_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "end_date_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frequency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "frequency_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "run_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "run_script_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduler_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_date_time" {
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
resource "avi_scheduler" "this" {
  # backup_config_ref - (optional) is a type of string
  backup_config_ref = var.backup_config_ref
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # end_date_time - (optional) is a type of string
  end_date_time = var.end_date_time
  # frequency - (optional) is a type of number
  frequency = var.frequency
  # frequency_unit - (optional) is a type of string
  frequency_unit = var.frequency_unit
  # name - (required) is a type of string
  name = var.name
  # run_mode - (optional) is a type of string
  run_mode = var.run_mode
  # run_script_ref - (optional) is a type of string
  run_script_ref = var.run_script_ref
  # scheduler_action - (optional) is a type of string
  scheduler_action = var.scheduler_action
  # start_date_time - (optional) is a type of string
  start_date_time = var.start_date_time
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "backup_config_ref" {
  description = "returns a string"
  value       = avi_scheduler.this.backup_config_ref
}

output "end_date_time" {
  description = "returns a string"
  value       = avi_scheduler.this.end_date_time
}

output "frequency" {
  description = "returns a number"
  value       = avi_scheduler.this.frequency
}

output "frequency_unit" {
  description = "returns a string"
  value       = avi_scheduler.this.frequency_unit
}

output "id" {
  description = "returns a string"
  value       = avi_scheduler.this.id
}

output "run_mode" {
  description = "returns a string"
  value       = avi_scheduler.this.run_mode
}

output "run_script_ref" {
  description = "returns a string"
  value       = avi_scheduler.this.run_script_ref
}

output "start_date_time" {
  description = "returns a string"
  value       = avi_scheduler.this.start_date_time
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_scheduler.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_scheduler.this.uuid
}

output "this" {
  value = avi_scheduler.this
}
```

[top](#index)