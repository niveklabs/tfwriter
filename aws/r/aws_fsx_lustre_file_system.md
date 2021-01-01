# aws_fsx_lustre_file_system
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_fsx_lustre_file_system" {
  source = "./modules/aws/r/aws_fsx_lustre_file_system"

  # auto_import_policy - (optional) is a type of string
  auto_import_policy = null
  # automatic_backup_retention_days - (optional) is a type of number
  automatic_backup_retention_days = null
  # copy_tags_to_backups - (optional) is a type of bool
  copy_tags_to_backups = null
  # daily_automatic_backup_start_time - (optional) is a type of string
  daily_automatic_backup_start_time = null
  # deployment_type - (optional) is a type of string
  deployment_type = null
  # drive_cache_type - (optional) is a type of string
  drive_cache_type = null
  # export_path - (optional) is a type of string
  export_path = null
  # import_path - (optional) is a type of string
  import_path = null
  # imported_file_chunk_size - (optional) is a type of number
  imported_file_chunk_size = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # per_unit_storage_throughput - (optional) is a type of number
  per_unit_storage_throughput = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # storage_capacity - (required) is a type of number
  storage_capacity = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # weekly_maintenance_start_time - (optional) is a type of string
  weekly_maintenance_start_time = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "auto_import_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "automatic_backup_retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "copy_tags_to_backups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "daily_automatic_backup_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drive_cache_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "export_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "imported_file_chunk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_unit_storage_throughput" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "storage_capacity" {
  description = "(required)"
  type        = number
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "weekly_maintenance_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_fsx_lustre_file_system" "this" {
  auto_import_policy                = var.auto_import_policy
  automatic_backup_retention_days   = var.automatic_backup_retention_days
  copy_tags_to_backups              = var.copy_tags_to_backups
  daily_automatic_backup_start_time = var.daily_automatic_backup_start_time
  deployment_type                   = var.deployment_type
  drive_cache_type                  = var.drive_cache_type
  export_path                       = var.export_path
  import_path                       = var.import_path
  imported_file_chunk_size          = var.imported_file_chunk_size
  kms_key_id                        = var.kms_key_id
  per_unit_storage_throughput       = var.per_unit_storage_throughput
  security_group_ids                = var.security_group_ids
  storage_capacity                  = var.storage_capacity
  storage_type                      = var.storage_type
  subnet_ids                        = var.subnet_ids
  tags                              = var.tags
  weekly_maintenance_start_time     = var.weekly_maintenance_start_time

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.arn
}

output "auto_import_policy" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.auto_import_policy
}

output "automatic_backup_retention_days" {
  description = "returns a number"
  value       = aws_fsx_lustre_file_system.this.automatic_backup_retention_days
}

output "daily_automatic_backup_start_time" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.daily_automatic_backup_start_time
}

output "dns_name" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.dns_name
}

output "export_path" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.export_path
}

output "id" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.id
}

output "imported_file_chunk_size" {
  description = "returns a number"
  value       = aws_fsx_lustre_file_system.this.imported_file_chunk_size
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.kms_key_id
}

output "mount_name" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.mount_name
}

output "network_interface_ids" {
  description = "returns a list of string"
  value       = aws_fsx_lustre_file_system.this.network_interface_ids
}

output "owner_id" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.owner_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.vpc_id
}

output "weekly_maintenance_start_time" {
  description = "returns a string"
  value       = aws_fsx_lustre_file_system.this.weekly_maintenance_start_time
}

output "this" {
  value = aws_fsx_lustre_file_system.this
}
```
[top](#index)
