# aws_docdb_cluster

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_docdb_cluster" {
  source = "./modules/aws/r/aws_docdb_cluster"

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
  # cluster_members - (optional) is a type of set of string
  cluster_members = []
  # db_cluster_parameter_group_name - (optional) is a type of string
  db_cluster_parameter_group_name = null
  # db_subnet_group_name - (optional) is a type of string
  db_subnet_group_name = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # enabled_cloudwatch_logs_exports - (optional) is a type of list of string
  enabled_cloudwatch_logs_exports = []
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = null
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

```hcl
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

variable "cluster_members" {
  description = "(optional)"
  type        = set(string)
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

variable "enabled_cloudwatch_logs_exports" {
  description = "(optional)"
  type        = list(string)
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
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "aws_docdb_cluster" "this" {
  apply_immediately               = var.apply_immediately
  availability_zones              = var.availability_zones
  backup_retention_period         = var.backup_retention_period
  cluster_identifier              = var.cluster_identifier
  cluster_identifier_prefix       = var.cluster_identifier_prefix
  cluster_members                 = var.cluster_members
  db_cluster_parameter_group_name = var.db_cluster_parameter_group_name
  db_subnet_group_name            = var.db_subnet_group_name
  deletion_protection             = var.deletion_protection
  enabled_cloudwatch_logs_exports = var.enabled_cloudwatch_logs_exports
  engine                          = var.engine
  engine_version                  = var.engine_version
  final_snapshot_identifier       = var.final_snapshot_identifier
  kms_key_id                      = var.kms_key_id
  master_password                 = var.master_password
  master_username                 = var.master_username
  port                            = var.port
  preferred_backup_window         = var.preferred_backup_window
  preferred_maintenance_window    = var.preferred_maintenance_window
  skip_final_snapshot             = var.skip_final_snapshot
  snapshot_identifier             = var.snapshot_identifier
  storage_encrypted               = var.storage_encrypted
  tags                            = var.tags
  vpc_security_group_ids          = var.vpc_security_group_ids

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

```hcl
output "apply_immediately" {
  description = "returns a bool"
  value       = aws_docdb_cluster.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = aws_docdb_cluster.this.availability_zones
}

output "cluster_identifier" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.cluster_identifier
}

output "cluster_identifier_prefix" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.cluster_identifier_prefix
}

output "cluster_members" {
  description = "returns a set of string"
  value       = aws_docdb_cluster.this.cluster_members
}

output "cluster_resource_id" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.cluster_resource_id
}

output "db_cluster_parameter_group_name" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.db_cluster_parameter_group_name
}

output "db_subnet_group_name" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.db_subnet_group_name
}

output "endpoint" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.endpoint
}

output "engine_version" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.engine_version
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.kms_key_id
}

output "master_username" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.master_username
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.preferred_maintenance_window
}

output "reader_endpoint" {
  description = "returns a string"
  value       = aws_docdb_cluster.this.reader_endpoint
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_docdb_cluster.this.vpc_security_group_ids
}

output "this" {
  value = aws_docdb_cluster.this
}
```

[top](#index)