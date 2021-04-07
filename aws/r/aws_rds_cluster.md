# aws_rds_cluster

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_rds_cluster" {
  source = "./modules/aws/r/aws_rds_cluster"

  # allow_major_version_upgrade - (optional) is a type of bool
  allow_major_version_upgrade = null
  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # availability_zones - (optional) is a type of set of string
  availability_zones = []
  # backtrack_window - (optional) is a type of number
  backtrack_window = null
  # backup_retention_period - (optional) is a type of number
  backup_retention_period = null
  # cluster_identifier - (optional) is a type of string
  cluster_identifier = null
  # cluster_identifier_prefix - (optional) is a type of string
  cluster_identifier_prefix = null
  # cluster_members - (optional) is a type of set of string
  cluster_members = []
  # copy_tags_to_snapshot - (optional) is a type of bool
  copy_tags_to_snapshot = null
  # database_name - (optional) is a type of string
  database_name = null
  # db_cluster_parameter_group_name - (optional) is a type of string
  db_cluster_parameter_group_name = null
  # db_subnet_group_name - (optional) is a type of string
  db_subnet_group_name = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # enable_http_endpoint - (optional) is a type of bool
  enable_http_endpoint = null
  # enabled_cloudwatch_logs_exports - (optional) is a type of set of string
  enabled_cloudwatch_logs_exports = []
  # engine - (optional) is a type of string
  engine = null
  # engine_mode - (optional) is a type of string
  engine_mode = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = null
  # global_cluster_identifier - (optional) is a type of string
  global_cluster_identifier = null
  # iam_database_authentication_enabled - (optional) is a type of bool
  iam_database_authentication_enabled = null
  # iam_roles - (optional) is a type of set of string
  iam_roles = []
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # master_password - (optional) is a type of string
  master_password = null
  # master_username - (optional) is a type of string
  master_username = null
  # port - (optional) is a type of number
  port = null
  # preferred_backup_window - (optional) is a type of string
  preferred_backup_window = null
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = null
  # replication_source_identifier - (optional) is a type of string
  replication_source_identifier = null
  # skip_final_snapshot - (optional) is a type of bool
  skip_final_snapshot = null
  # snapshot_identifier - (optional) is a type of string
  snapshot_identifier = null
  # source_region - (optional) is a type of string
  source_region = null
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

  restore_to_point_in_time = [{
    restore_to_time            = null
    restore_type               = null
    source_cluster_identifier  = null
    use_latest_restorable_time = null
  }]

  s3_import = [{
    bucket_name           = null
    bucket_prefix         = null
    ingestion_role        = null
    source_engine         = null
    source_engine_version = null
  }]

  scaling_configuration = [{
    auto_pause               = null
    max_capacity             = null
    min_capacity             = null
    seconds_until_auto_pause = null
    timeout_action           = null
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

variable "availability_zones" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backtrack_window" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backup_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cluster_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_identifier_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_members" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "copy_tags_to_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_subnet_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_http_endpoint" {
  description = "(optional)"
  type        = bool
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

variable "engine_mode" {
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

variable "global_cluster_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_database_authentication_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "iam_roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preferred_backup_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replication_source_identifier" {
  description = "(optional)"
  type        = string
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

variable "source_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
      restore_to_time            = string
      restore_type               = string
      source_cluster_identifier  = string
      use_latest_restorable_time = bool
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

variable "scaling_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_pause               = bool
      max_capacity             = number
      min_capacity             = number
      seconds_until_auto_pause = number
      timeout_action           = string
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
resource "aws_rds_cluster" "this" {
  # allow_major_version_upgrade - (optional) is a type of bool
  allow_major_version_upgrade = var.allow_major_version_upgrade
  # apply_immediately - (optional) is a type of bool
  apply_immediately = var.apply_immediately
  # availability_zones - (optional) is a type of set of string
  availability_zones = var.availability_zones
  # backtrack_window - (optional) is a type of number
  backtrack_window = var.backtrack_window
  # backup_retention_period - (optional) is a type of number
  backup_retention_period = var.backup_retention_period
  # cluster_identifier - (optional) is a type of string
  cluster_identifier = var.cluster_identifier
  # cluster_identifier_prefix - (optional) is a type of string
  cluster_identifier_prefix = var.cluster_identifier_prefix
  # cluster_members - (optional) is a type of set of string
  cluster_members = var.cluster_members
  # copy_tags_to_snapshot - (optional) is a type of bool
  copy_tags_to_snapshot = var.copy_tags_to_snapshot
  # database_name - (optional) is a type of string
  database_name = var.database_name
  # db_cluster_parameter_group_name - (optional) is a type of string
  db_cluster_parameter_group_name = var.db_cluster_parameter_group_name
  # db_subnet_group_name - (optional) is a type of string
  db_subnet_group_name = var.db_subnet_group_name
  # deletion_protection - (optional) is a type of bool
  deletion_protection = var.deletion_protection
  # enable_http_endpoint - (optional) is a type of bool
  enable_http_endpoint = var.enable_http_endpoint
  # enabled_cloudwatch_logs_exports - (optional) is a type of set of string
  enabled_cloudwatch_logs_exports = var.enabled_cloudwatch_logs_exports
  # engine - (optional) is a type of string
  engine = var.engine
  # engine_mode - (optional) is a type of string
  engine_mode = var.engine_mode
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = var.final_snapshot_identifier
  # global_cluster_identifier - (optional) is a type of string
  global_cluster_identifier = var.global_cluster_identifier
  # iam_database_authentication_enabled - (optional) is a type of bool
  iam_database_authentication_enabled = var.iam_database_authentication_enabled
  # iam_roles - (optional) is a type of set of string
  iam_roles = var.iam_roles
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # master_password - (optional) is a type of string
  master_password = var.master_password
  # master_username - (optional) is a type of string
  master_username = var.master_username
  # port - (optional) is a type of number
  port = var.port
  # preferred_backup_window - (optional) is a type of string
  preferred_backup_window = var.preferred_backup_window
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = var.preferred_maintenance_window
  # replication_source_identifier - (optional) is a type of string
  replication_source_identifier = var.replication_source_identifier
  # skip_final_snapshot - (optional) is a type of bool
  skip_final_snapshot = var.skip_final_snapshot
  # snapshot_identifier - (optional) is a type of string
  snapshot_identifier = var.snapshot_identifier
  # source_region - (optional) is a type of string
  source_region = var.source_region
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = var.storage_encrypted
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = var.vpc_security_group_ids

  dynamic "restore_to_point_in_time" {
    for_each = var.restore_to_point_in_time
    content {
      # restore_to_time - (optional) is a type of string
      restore_to_time = restore_to_point_in_time.value["restore_to_time"]
      # restore_type - (optional) is a type of string
      restore_type = restore_to_point_in_time.value["restore_type"]
      # source_cluster_identifier - (required) is a type of string
      source_cluster_identifier = restore_to_point_in_time.value["source_cluster_identifier"]
      # use_latest_restorable_time - (optional) is a type of bool
      use_latest_restorable_time = restore_to_point_in_time.value["use_latest_restorable_time"]
    }
  }

  dynamic "s3_import" {
    for_each = var.s3_import
    content {
      # bucket_name - (required) is a type of string
      bucket_name = s3_import.value["bucket_name"]
      # bucket_prefix - (optional) is a type of string
      bucket_prefix = s3_import.value["bucket_prefix"]
      # ingestion_role - (required) is a type of string
      ingestion_role = s3_import.value["ingestion_role"]
      # source_engine - (required) is a type of string
      source_engine = s3_import.value["source_engine"]
      # source_engine_version - (required) is a type of string
      source_engine_version = s3_import.value["source_engine_version"]
    }
  }

  dynamic "scaling_configuration" {
    for_each = var.scaling_configuration
    content {
      # auto_pause - (optional) is a type of bool
      auto_pause = scaling_configuration.value["auto_pause"]
      # max_capacity - (optional) is a type of number
      max_capacity = scaling_configuration.value["max_capacity"]
      # min_capacity - (optional) is a type of number
      min_capacity = scaling_configuration.value["min_capacity"]
      # seconds_until_auto_pause - (optional) is a type of number
      seconds_until_auto_pause = scaling_configuration.value["seconds_until_auto_pause"]
      # timeout_action - (optional) is a type of string
      timeout_action = scaling_configuration.value["timeout_action"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "apply_immediately" {
  description = "returns a bool"
  value       = aws_rds_cluster.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_rds_cluster.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = aws_rds_cluster.this.availability_zones
}

output "cluster_identifier" {
  description = "returns a string"
  value       = aws_rds_cluster.this.cluster_identifier
}

output "cluster_identifier_prefix" {
  description = "returns a string"
  value       = aws_rds_cluster.this.cluster_identifier_prefix
}

output "cluster_members" {
  description = "returns a set of string"
  value       = aws_rds_cluster.this.cluster_members
}

output "cluster_resource_id" {
  description = "returns a string"
  value       = aws_rds_cluster.this.cluster_resource_id
}

output "database_name" {
  description = "returns a string"
  value       = aws_rds_cluster.this.database_name
}

output "db_cluster_parameter_group_name" {
  description = "returns a string"
  value       = aws_rds_cluster.this.db_cluster_parameter_group_name
}

output "db_subnet_group_name" {
  description = "returns a string"
  value       = aws_rds_cluster.this.db_subnet_group_name
}

output "endpoint" {
  description = "returns a string"
  value       = aws_rds_cluster.this.endpoint
}

output "engine_version" {
  description = "returns a string"
  value       = aws_rds_cluster.this.engine_version
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_rds_cluster.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_rds_cluster.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_rds_cluster.this.kms_key_id
}

output "master_username" {
  description = "returns a string"
  value       = aws_rds_cluster.this.master_username
}

output "port" {
  description = "returns a number"
  value       = aws_rds_cluster.this.port
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = aws_rds_cluster.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_rds_cluster.this.preferred_maintenance_window
}

output "reader_endpoint" {
  description = "returns a string"
  value       = aws_rds_cluster.this.reader_endpoint
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = aws_rds_cluster.this.storage_encrypted
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_rds_cluster.this.vpc_security_group_ids
}

output "this" {
  value = aws_rds_cluster.this
}
```

[top](#index)