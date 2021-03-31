# aws_fsx_windows_file_system

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_fsx_windows_file_system" {
  source = "./modules/aws/r/aws_fsx_windows_file_system"

  # active_directory_id - (optional) is a type of string
  active_directory_id = null
  # automatic_backup_retention_days - (optional) is a type of number
  automatic_backup_retention_days = null
  # copy_tags_to_backups - (optional) is a type of bool
  copy_tags_to_backups = null
  # daily_automatic_backup_start_time - (optional) is a type of string
  daily_automatic_backup_start_time = null
  # deployment_type - (optional) is a type of string
  deployment_type = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # preferred_subnet_id - (optional) is a type of string
  preferred_subnet_id = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # skip_final_backup - (optional) is a type of bool
  skip_final_backup = null
  # storage_capacity - (required) is a type of number
  storage_capacity = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # throughput_capacity - (required) is a type of number
  throughput_capacity = null
  # weekly_maintenance_start_time - (optional) is a type of string
  weekly_maintenance_start_time = null

  self_managed_active_directory = [{
    dns_ips                                = []
    domain_name                            = null
    file_system_administrators_group       = null
    organizational_unit_distinguished_name = null
    password                               = null
    username                               = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active_directory_id" {
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

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "skip_final_backup" {
  description = "(optional)"
  type        = bool
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

variable "throughput_capacity" {
  description = "(required)"
  type        = number
}

variable "weekly_maintenance_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "self_managed_active_directory" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dns_ips                                = set(string)
      domain_name                            = string
      file_system_administrators_group       = string
      organizational_unit_distinguished_name = string
      password                               = string
      username                               = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_fsx_windows_file_system" "this" {
  active_directory_id               = var.active_directory_id
  automatic_backup_retention_days   = var.automatic_backup_retention_days
  copy_tags_to_backups              = var.copy_tags_to_backups
  daily_automatic_backup_start_time = var.daily_automatic_backup_start_time
  deployment_type                   = var.deployment_type
  kms_key_id                        = var.kms_key_id
  preferred_subnet_id               = var.preferred_subnet_id
  security_group_ids                = var.security_group_ids
  skip_final_backup                 = var.skip_final_backup
  storage_capacity                  = var.storage_capacity
  storage_type                      = var.storage_type
  subnet_ids                        = var.subnet_ids
  tags                              = var.tags
  throughput_capacity               = var.throughput_capacity
  weekly_maintenance_start_time     = var.weekly_maintenance_start_time

  dynamic "self_managed_active_directory" {
    for_each = var.self_managed_active_directory
    content {
      dns_ips                                = self_managed_active_directory.value["dns_ips"]
      domain_name                            = self_managed_active_directory.value["domain_name"]
      file_system_administrators_group       = self_managed_active_directory.value["file_system_administrators_group"]
      organizational_unit_distinguished_name = self_managed_active_directory.value["organizational_unit_distinguished_name"]
      password                               = self_managed_active_directory.value["password"]
      username                               = self_managed_active_directory.value["username"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.arn
}

output "daily_automatic_backup_start_time" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.daily_automatic_backup_start_time
}

output "dns_name" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.kms_key_id
}

output "network_interface_ids" {
  description = "returns a set of string"
  value       = aws_fsx_windows_file_system.this.network_interface_ids
}

output "owner_id" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.owner_id
}

output "preferred_file_server_ip" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.preferred_file_server_ip
}

output "preferred_subnet_id" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.preferred_subnet_id
}

output "remote_administration_endpoint" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.remote_administration_endpoint
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.vpc_id
}

output "weekly_maintenance_start_time" {
  description = "returns a string"
  value       = aws_fsx_windows_file_system.this.weekly_maintenance_start_time
}

output "this" {
  value = aws_fsx_windows_file_system.this
}
```

[top](#index)