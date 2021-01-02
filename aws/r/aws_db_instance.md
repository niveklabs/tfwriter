# aws_db_instance

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_db_instance" {
  source = "./modules/aws/r/aws_db_instance"

  # allocated_storage - (optional) is a type of number
  allocated_storage = null
  # allow_major_version_upgrade - (optional) is a type of bool
  allow_major_version_upgrade = null
  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # backup_retention_period - (optional) is a type of number
  backup_retention_period = null
  # backup_window - (optional) is a type of string
  backup_window = null
  # ca_cert_identifier - (optional) is a type of string
  ca_cert_identifier = null
  # character_set_name - (optional) is a type of string
  character_set_name = null
  # copy_tags_to_snapshot - (optional) is a type of bool
  copy_tags_to_snapshot = null
  # db_subnet_group_name - (optional) is a type of string
  db_subnet_group_name = null
  # delete_automated_backups - (optional) is a type of bool
  delete_automated_backups = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # domain - (optional) is a type of string
  domain = null
  # domain_iam_role_name - (optional) is a type of string
  domain_iam_role_name = null
  # enabled_cloudwatch_logs_exports - (optional) is a type of set of string
  enabled_cloudwatch_logs_exports = []
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = null
  # iam_database_authentication_enabled - (optional) is a type of bool
  iam_database_authentication_enabled = null
  # identifier - (optional) is a type of string
  identifier = null
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = null
  # instance_class - (required) is a type of string
  instance_class = null
  # iops - (optional) is a type of number
  iops = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # license_model - (optional) is a type of string
  license_model = null
  # maintenance_window - (optional) is a type of string
  maintenance_window = null
  # max_allocated_storage - (optional) is a type of number
  max_allocated_storage = null
  # monitoring_interval - (optional) is a type of number
  monitoring_interval = null
  # monitoring_role_arn - (optional) is a type of string
  monitoring_role_arn = null
  # multi_az - (optional) is a type of bool
  multi_az = null
  # name - (optional) is a type of string
  name = null
  # option_group_name - (optional) is a type of string
  option_group_name = null
  # parameter_group_name - (optional) is a type of string
  parameter_group_name = null
  # password - (optional) is a type of string
  password = null
  # performance_insights_enabled - (optional) is a type of bool
  performance_insights_enabled = null
  # performance_insights_kms_key_id - (optional) is a type of string
  performance_insights_kms_key_id = null
  # performance_insights_retention_period - (optional) is a type of number
  performance_insights_retention_period = null
  # port - (optional) is a type of number
  port = null
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = null
  # replicate_source_db - (optional) is a type of string
  replicate_source_db = null
  # security_group_names - (optional) is a type of set of string
  security_group_names = []
  # skip_final_snapshot - (optional) is a type of bool
  skip_final_snapshot = null
  # snapshot_identifier - (optional) is a type of string
  snapshot_identifier = null
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timezone - (optional) is a type of string
  timezone = null
  # username - (optional) is a type of string
  username = null
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

  restore_to_point_in_time = [{
    restore_time                  = null
    source_db_instance_identifier = null
    source_dbi_resource_id        = null
    use_latest_restorable_time    = null
  }]

  s3_import = [{
    bucket_name           = null
    bucket_prefix         = null
    ingestion_role        = null
    source_engine         = null
    source_engine_version = null
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
variable "allocated_storage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allow_major_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "apply_immediately" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_minor_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backup_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ca_cert_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "character_set_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "copy_tags_to_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "db_subnet_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_automated_backups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_iam_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled_cloudwatch_logs_exports" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "final_snapshot_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_database_authentication_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_class" {
  description = "(required)"
  type        = string
}

variable "iops" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_allocated_storage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitoring_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitoring_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi_az" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "option_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "performance_insights_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "performance_insights_kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "performance_insights_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "publicly_accessible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "replicate_source_db" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "skip_final_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "snapshot_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "restore_to_point_in_time" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      restore_time                  = string
      source_db_instance_identifier = string
      source_dbi_resource_id        = string
      use_latest_restorable_time    = bool
    }
  ))
  default = []
}

variable "s3_import" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_name           = string
      bucket_prefix         = string
      ingestion_role        = string
      source_engine         = string
      source_engine_version = string
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
resource "aws_db_instance" "this" {
  allocated_storage                     = var.allocated_storage
  allow_major_version_upgrade           = var.allow_major_version_upgrade
  apply_immediately                     = var.apply_immediately
  auto_minor_version_upgrade            = var.auto_minor_version_upgrade
  availability_zone                     = var.availability_zone
  backup_retention_period               = var.backup_retention_period
  backup_window                         = var.backup_window
  ca_cert_identifier                    = var.ca_cert_identifier
  character_set_name                    = var.character_set_name
  copy_tags_to_snapshot                 = var.copy_tags_to_snapshot
  db_subnet_group_name                  = var.db_subnet_group_name
  delete_automated_backups              = var.delete_automated_backups
  deletion_protection                   = var.deletion_protection
  domain                                = var.domain
  domain_iam_role_name                  = var.domain_iam_role_name
  enabled_cloudwatch_logs_exports       = var.enabled_cloudwatch_logs_exports
  engine                                = var.engine
  engine_version                        = var.engine_version
  final_snapshot_identifier             = var.final_snapshot_identifier
  iam_database_authentication_enabled   = var.iam_database_authentication_enabled
  identifier                            = var.identifier
  identifier_prefix                     = var.identifier_prefix
  instance_class                        = var.instance_class
  iops                                  = var.iops
  kms_key_id                            = var.kms_key_id
  license_model                         = var.license_model
  maintenance_window                    = var.maintenance_window
  max_allocated_storage                 = var.max_allocated_storage
  monitoring_interval                   = var.monitoring_interval
  monitoring_role_arn                   = var.monitoring_role_arn
  multi_az                              = var.multi_az
  name                                  = var.name
  option_group_name                     = var.option_group_name
  parameter_group_name                  = var.parameter_group_name
  password                              = var.password
  performance_insights_enabled          = var.performance_insights_enabled
  performance_insights_kms_key_id       = var.performance_insights_kms_key_id
  performance_insights_retention_period = var.performance_insights_retention_period
  port                                  = var.port
  publicly_accessible                   = var.publicly_accessible
  replicate_source_db                   = var.replicate_source_db
  security_group_names                  = var.security_group_names
  skip_final_snapshot                   = var.skip_final_snapshot
  snapshot_identifier                   = var.snapshot_identifier
  storage_encrypted                     = var.storage_encrypted
  storage_type                          = var.storage_type
  tags                                  = var.tags
  timezone                              = var.timezone
  username                              = var.username
  vpc_security_group_ids                = var.vpc_security_group_ids

  dynamic "restore_to_point_in_time" {
    for_each = var.restore_to_point_in_time
    content {
      restore_time                  = restore_to_point_in_time.value["restore_time"]
      source_db_instance_identifier = restore_to_point_in_time.value["source_db_instance_identifier"]
      source_dbi_resource_id        = restore_to_point_in_time.value["source_dbi_resource_id"]
      use_latest_restorable_time    = restore_to_point_in_time.value["use_latest_restorable_time"]
    }
  }

  dynamic "s3_import" {
    for_each = var.s3_import
    content {
      bucket_name           = s3_import.value["bucket_name"]
      bucket_prefix         = s3_import.value["bucket_prefix"]
      ingestion_role        = s3_import.value["ingestion_role"]
      source_engine         = s3_import.value["source_engine"]
      source_engine_version = s3_import.value["source_engine_version"]
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
output "address" {
  description = "returns a string"
  value       = aws_db_instance.this.address
}

output "allocated_storage" {
  description = "returns a number"
  value       = aws_db_instance.this.allocated_storage
}

output "apply_immediately" {
  description = "returns a bool"
  value       = aws_db_instance.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_db_instance.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_db_instance.this.availability_zone
}

output "backup_retention_period" {
  description = "returns a number"
  value       = aws_db_instance.this.backup_retention_period
}

output "backup_window" {
  description = "returns a string"
  value       = aws_db_instance.this.backup_window
}

output "ca_cert_identifier" {
  description = "returns a string"
  value       = aws_db_instance.this.ca_cert_identifier
}

output "character_set_name" {
  description = "returns a string"
  value       = aws_db_instance.this.character_set_name
}

output "db_subnet_group_name" {
  description = "returns a string"
  value       = aws_db_instance.this.db_subnet_group_name
}

output "endpoint" {
  description = "returns a string"
  value       = aws_db_instance.this.endpoint
}

output "engine" {
  description = "returns a string"
  value       = aws_db_instance.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = aws_db_instance.this.engine_version
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_db_instance.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_db_instance.this.id
}

output "identifier" {
  description = "returns a string"
  value       = aws_db_instance.this.identifier
}

output "identifier_prefix" {
  description = "returns a string"
  value       = aws_db_instance.this.identifier_prefix
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_db_instance.this.kms_key_id
}

output "latest_restorable_time" {
  description = "returns a string"
  value       = aws_db_instance.this.latest_restorable_time
}

output "license_model" {
  description = "returns a string"
  value       = aws_db_instance.this.license_model
}

output "maintenance_window" {
  description = "returns a string"
  value       = aws_db_instance.this.maintenance_window
}

output "monitoring_role_arn" {
  description = "returns a string"
  value       = aws_db_instance.this.monitoring_role_arn
}

output "multi_az" {
  description = "returns a bool"
  value       = aws_db_instance.this.multi_az
}

output "name" {
  description = "returns a string"
  value       = aws_db_instance.this.name
}

output "option_group_name" {
  description = "returns a string"
  value       = aws_db_instance.this.option_group_name
}

output "parameter_group_name" {
  description = "returns a string"
  value       = aws_db_instance.this.parameter_group_name
}

output "performance_insights_kms_key_id" {
  description = "returns a string"
  value       = aws_db_instance.this.performance_insights_kms_key_id
}

output "performance_insights_retention_period" {
  description = "returns a number"
  value       = aws_db_instance.this.performance_insights_retention_period
}

output "port" {
  description = "returns a number"
  value       = aws_db_instance.this.port
}

output "replicas" {
  description = "returns a list of string"
  value       = aws_db_instance.this.replicas
}

output "resource_id" {
  description = "returns a string"
  value       = aws_db_instance.this.resource_id
}

output "status" {
  description = "returns a string"
  value       = aws_db_instance.this.status
}

output "storage_type" {
  description = "returns a string"
  value       = aws_db_instance.this.storage_type
}

output "timezone" {
  description = "returns a string"
  value       = aws_db_instance.this.timezone
}

output "username" {
  description = "returns a string"
  value       = aws_db_instance.this.username
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_db_instance.this.vpc_security_group_ids
}

output "this" {
  value = aws_db_instance.this
}
```

[top](#index)