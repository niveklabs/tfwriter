# avi_backup

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
module "avi_backup" {
  source = "./modules/avi/r/avi_backup"

  # backup_config_ref - (optional) is a type of string
  backup_config_ref = null
  # file_name - (required) is a type of string
  file_name = null
  # local_file_url - (optional) is a type of string
  local_file_url = null
  # remote_file_url - (optional) is a type of string
  remote_file_url = null
  # scheduler_ref - (optional) is a type of string
  scheduler_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # timestamp - (optional) is a type of string
  timestamp = null
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

variable "file_name" {
  description = "(required)"
  type        = string
}

variable "local_file_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_file_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduler_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timestamp" {
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
resource "avi_backup" "this" {
  # backup_config_ref - (optional) is a type of string
  backup_config_ref = var.backup_config_ref
  # file_name - (required) is a type of string
  file_name = var.file_name
  # local_file_url - (optional) is a type of string
  local_file_url = var.local_file_url
  # remote_file_url - (optional) is a type of string
  remote_file_url = var.remote_file_url
  # scheduler_ref - (optional) is a type of string
  scheduler_ref = var.scheduler_ref
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # timestamp - (optional) is a type of string
  timestamp = var.timestamp
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "backup_config_ref" {
  description = "returns a string"
  value       = avi_backup.this.backup_config_ref
}

output "id" {
  description = "returns a string"
  value       = avi_backup.this.id
}

output "local_file_url" {
  description = "returns a string"
  value       = avi_backup.this.local_file_url
}

output "remote_file_url" {
  description = "returns a string"
  value       = avi_backup.this.remote_file_url
}

output "scheduler_ref" {
  description = "returns a string"
  value       = avi_backup.this.scheduler_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_backup.this.tenant_ref
}

output "timestamp" {
  description = "returns a string"
  value       = avi_backup.this.timestamp
}

output "uuid" {
  description = "returns a string"
  value       = avi_backup.this.uuid
}

output "this" {
  value = avi_backup.this
}
```

[top](#index)