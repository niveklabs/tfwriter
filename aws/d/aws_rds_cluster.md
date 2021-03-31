# aws_rds_cluster

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_rds_cluster" {
  source = "./modules/aws/d/aws_rds_cluster"

  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_rds_cluster" "this" {
  cluster_identifier = var.cluster_identifier
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = data.aws_rds_cluster.this.availability_zones
}

output "backtrack_window" {
  description = "returns a number"
  value       = data.aws_rds_cluster.this.backtrack_window
}

output "backup_retention_period" {
  description = "returns a number"
  value       = data.aws_rds_cluster.this.backup_retention_period
}

output "cluster_members" {
  description = "returns a set of string"
  value       = data.aws_rds_cluster.this.cluster_members
}

output "cluster_resource_id" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.cluster_resource_id
}

output "database_name" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.database_name
}

output "db_cluster_parameter_group_name" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.db_cluster_parameter_group_name
}

output "db_subnet_group_name" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.db_subnet_group_name
}

output "enabled_cloudwatch_logs_exports" {
  description = "returns a list of string"
  value       = data.aws_rds_cluster.this.enabled_cloudwatch_logs_exports
}

output "endpoint" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.endpoint
}

output "engine" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.engine_version
}

output "final_snapshot_identifier" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.final_snapshot_identifier
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.hosted_zone_id
}

output "iam_database_authentication_enabled" {
  description = "returns a bool"
  value       = data.aws_rds_cluster.this.iam_database_authentication_enabled
}

output "iam_roles" {
  description = "returns a set of string"
  value       = data.aws_rds_cluster.this.iam_roles
}

output "id" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.kms_key_id
}

output "master_username" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.master_username
}

output "port" {
  description = "returns a number"
  value       = data.aws_rds_cluster.this.port
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.preferred_maintenance_window
}

output "reader_endpoint" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.reader_endpoint
}

output "replication_source_identifier" {
  description = "returns a string"
  value       = data.aws_rds_cluster.this.replication_source_identifier
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = data.aws_rds_cluster.this.storage_encrypted
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_rds_cluster.this.tags
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = data.aws_rds_cluster.this.vpc_security_group_ids
}

output "this" {
  value = aws_rds_cluster.this
}
```

[top](#index)