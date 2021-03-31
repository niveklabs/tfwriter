# avi_scheduler

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
module "avi_scheduler" {
  source = "./modules/avi/d/avi_scheduler"

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
data "avi_scheduler" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "backup_config_ref" {
  description = "returns a string"
  value       = data.avi_scheduler.this.backup_config_ref
}

output "enabled" {
  description = "returns a bool"
  value       = data.avi_scheduler.this.enabled
}

output "end_date_time" {
  description = "returns a string"
  value       = data.avi_scheduler.this.end_date_time
}

output "frequency" {
  description = "returns a number"
  value       = data.avi_scheduler.this.frequency
}

output "frequency_unit" {
  description = "returns a string"
  value       = data.avi_scheduler.this.frequency_unit
}

output "id" {
  description = "returns a string"
  value       = data.avi_scheduler.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_scheduler.this.name
}

output "run_mode" {
  description = "returns a string"
  value       = data.avi_scheduler.this.run_mode
}

output "run_script_ref" {
  description = "returns a string"
  value       = data.avi_scheduler.this.run_script_ref
}

output "scheduler_action" {
  description = "returns a string"
  value       = data.avi_scheduler.this.scheduler_action
}

output "start_date_time" {
  description = "returns a string"
  value       = data.avi_scheduler.this.start_date_time
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_scheduler.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_scheduler.this.uuid
}

output "this" {
  value = avi_scheduler.this
}
```

[top](#index)