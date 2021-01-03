# alicloud_db_backup_policy

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_db_backup_policy" {
  source = "./modules/alicloud/r/alicloud_db_backup_policy"

  # archive_backup_keep_count - (optional) is a type of number
  archive_backup_keep_count = null
  # archive_backup_keep_policy - (optional) is a type of string
  archive_backup_keep_policy = null
  # archive_backup_retention_period - (optional) is a type of number
  archive_backup_retention_period = null
  # backup_period - (optional) is a type of set of string
  backup_period = []
  # backup_retention_period - (optional) is a type of number
  backup_retention_period = null
  # backup_time - (optional) is a type of string
  backup_time = null
  # compress_type - (optional) is a type of string
  compress_type = null
  # enable_backup_log - (optional) is a type of bool
  enable_backup_log = null
  # high_space_usage_protection - (optional) is a type of string
  high_space_usage_protection = null
  # instance_id - (required) is a type of string
  instance_id = null
  # local_log_retention_hours - (optional) is a type of number
  local_log_retention_hours = null
  # local_log_retention_space - (optional) is a type of number
  local_log_retention_space = null
  # log_backup - (optional) is a type of bool
  log_backup = null
  # log_backup_frequency - (optional) is a type of string
  log_backup_frequency = null
  # log_backup_retention_period - (optional) is a type of number
  log_backup_retention_period = null
  # log_retention_period - (optional) is a type of number
  log_retention_period = null
  # preferred_backup_period - (optional) is a type of set of string
  preferred_backup_period = []
  # preferred_backup_time - (optional) is a type of string
  preferred_backup_time = null
  # retention_period - (optional) is a type of number
  retention_period = null
}
```

[top](#index)

### Variables

```terraform
variable "archive_backup_keep_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "archive_backup_keep_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "archive_backup_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backup_period" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backup_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compress_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_backup_log" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "high_space_usage_protection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "local_log_retention_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_log_retention_space" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_backup" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_backup_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_backup_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preferred_backup_period" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "preferred_backup_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_backup_policy" "this" {
  archive_backup_keep_count       = var.archive_backup_keep_count
  archive_backup_keep_policy      = var.archive_backup_keep_policy
  archive_backup_retention_period = var.archive_backup_retention_period
  backup_period                   = var.backup_period
  backup_retention_period         = var.backup_retention_period
  backup_time                     = var.backup_time
  compress_type                   = var.compress_type
  enable_backup_log               = var.enable_backup_log
  high_space_usage_protection     = var.high_space_usage_protection
  instance_id                     = var.instance_id
  local_log_retention_hours       = var.local_log_retention_hours
  local_log_retention_space       = var.local_log_retention_space
  log_backup                      = var.log_backup
  log_backup_frequency            = var.log_backup_frequency
  log_backup_retention_period     = var.log_backup_retention_period
  log_retention_period            = var.log_retention_period
  preferred_backup_period         = var.preferred_backup_period
  preferred_backup_time           = var.preferred_backup_time
  retention_period                = var.retention_period
}
```

[top](#index)

### Outputs

```terraform
output "archive_backup_keep_count" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.archive_backup_keep_count
}

output "archive_backup_keep_policy" {
  description = "returns a string"
  value       = alicloud_db_backup_policy.this.archive_backup_keep_policy
}

output "archive_backup_retention_period" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.archive_backup_retention_period
}

output "backup_period" {
  description = "returns a set of string"
  value       = alicloud_db_backup_policy.this.backup_period
}

output "backup_time" {
  description = "returns a string"
  value       = alicloud_db_backup_policy.this.backup_time
}

output "compress_type" {
  description = "returns a string"
  value       = alicloud_db_backup_policy.this.compress_type
}

output "enable_backup_log" {
  description = "returns a bool"
  value       = alicloud_db_backup_policy.this.enable_backup_log
}

output "id" {
  description = "returns a string"
  value       = alicloud_db_backup_policy.this.id
}

output "local_log_retention_hours" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.local_log_retention_hours
}

output "local_log_retention_space" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.local_log_retention_space
}

output "log_backup" {
  description = "returns a bool"
  value       = alicloud_db_backup_policy.this.log_backup
}

output "log_backup_frequency" {
  description = "returns a string"
  value       = alicloud_db_backup_policy.this.log_backup_frequency
}

output "log_backup_retention_period" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.log_backup_retention_period
}

output "log_retention_period" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.log_retention_period
}

output "preferred_backup_period" {
  description = "returns a set of string"
  value       = alicloud_db_backup_policy.this.preferred_backup_period
}

output "retention_period" {
  description = "returns a number"
  value       = alicloud_db_backup_policy.this.retention_period
}

output "this" {
  value = alicloud_db_backup_policy.this
}
```

[top](#index)