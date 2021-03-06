# aws_neptune_cluster

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
module "aws_neptune_cluster" {
  source = "./modules/aws/r/aws_neptune_cluster"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # availability_zones - (optional) is a type of set of string
  availability_zones = []
  # backup_retention_period - (optional) is a type of number
  backup_retention_period = null
  # cluster_identifier - (optional) is a type of string
  cluster_identifier = null
  # cluster_identifier_prefix - (optional) is a type of string
  cluster_identifier_prefix = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # enable_cloudwatch_logs_exports - (optional) is a type of set of string
  enable_cloudwatch_logs_exports = []
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = null
  # iam_database_authentication_enabled - (optional) is a type of bool
  iam_database_authentication_enabled = null
  # iam_roles - (optional) is a type of set of string
  iam_roles = []
  # kms_key_arn - (optional) is a type of string
  kms_key_arn = null
  # neptune_cluster_parameter_group_name - (optional) is a type of string
  neptune_cluster_parameter_group_name = null
  # neptune_subnet_group_name - (optional) is a type of string
  neptune_subnet_group_name = null
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
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

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

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_cloudwatch_logs_exports" {
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

variable "iam_roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "neptune_cluster_parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "neptune_subnet_group_name" {
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
resource "aws_neptune_cluster" "this" {
  # apply_immediately - (optional) is a type of bool
  apply_immediately = var.apply_immediately
  # availability_zones - (optional) is a type of set of string
  availability_zones = var.availability_zones
  # backup_retention_period - (optional) is a type of number
  backup_retention_period = var.backup_retention_period
  # cluster_identifier - (optional) is a type of string
  cluster_identifier = var.cluster_identifier
  # cluster_identifier_prefix - (optional) is a type of string
  cluster_identifier_prefix = var.cluster_identifier_prefix
  # deletion_protection - (optional) is a type of bool
  deletion_protection = var.deletion_protection
  # enable_cloudwatch_logs_exports - (optional) is a type of set of string
  enable_cloudwatch_logs_exports = var.enable_cloudwatch_logs_exports
  # engine - (optional) is a type of string
  engine = var.engine
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = var.final_snapshot_identifier
  # iam_database_authentication_enabled - (optional) is a type of bool
  iam_database_authentication_enabled = var.iam_database_authentication_enabled
  # iam_roles - (optional) is a type of set of string
  iam_roles = var.iam_roles
  # kms_key_arn - (optional) is a type of string
  kms_key_arn = var.kms_key_arn
  # neptune_cluster_parameter_group_name - (optional) is a type of string
  neptune_cluster_parameter_group_name = var.neptune_cluster_parameter_group_name
  # neptune_subnet_group_name - (optional) is a type of string
  neptune_subnet_group_name = var.neptune_subnet_group_name
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
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = var.storage_encrypted
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = var.vpc_security_group_ids

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
  value       = aws_neptune_cluster.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = aws_neptune_cluster.this.availability_zones
}

output "cluster_identifier" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.cluster_identifier
}

output "cluster_identifier_prefix" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.cluster_identifier_prefix
}

output "cluster_members" {
  description = "returns a set of string"
  value       = aws_neptune_cluster.this.cluster_members
}

output "cluster_resource_id" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.cluster_resource_id
}

output "endpoint" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.endpoint
}

output "engine_version" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.engine_version
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.id
}

output "kms_key_arn" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.kms_key_arn
}

output "neptune_subnet_group_name" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.neptune_subnet_group_name
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.preferred_maintenance_window
}

output "reader_endpoint" {
  description = "returns a string"
  value       = aws_neptune_cluster.this.reader_endpoint
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_neptune_cluster.this.vpc_security_group_ids
}

output "this" {
  value = aws_neptune_cluster.this
}
```

[top](#index)