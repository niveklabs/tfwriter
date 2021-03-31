# aws_db_instance

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
module "aws_db_instance" {
  source = "./modules/aws/d/aws_db_instance"

  # db_instance_identifier - (required) is a type of string
  db_instance_identifier = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "db_instance_identifier" {
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
data "aws_db_instance" "this" {
  db_instance_identifier = var.db_instance_identifier
  tags                   = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.aws_db_instance.this.address
}

output "allocated_storage" {
  description = "returns a number"
  value       = data.aws_db_instance.this.allocated_storage
}

output "auto_minor_version_upgrade" {
  description = "returns a bool"
  value       = data.aws_db_instance.this.auto_minor_version_upgrade
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_db_instance.this.availability_zone
}

output "backup_retention_period" {
  description = "returns a number"
  value       = data.aws_db_instance.this.backup_retention_period
}

output "ca_cert_identifier" {
  description = "returns a string"
  value       = data.aws_db_instance.this.ca_cert_identifier
}

output "db_cluster_identifier" {
  description = "returns a string"
  value       = data.aws_db_instance.this.db_cluster_identifier
}

output "db_instance_arn" {
  description = "returns a string"
  value       = data.aws_db_instance.this.db_instance_arn
}

output "db_instance_class" {
  description = "returns a string"
  value       = data.aws_db_instance.this.db_instance_class
}

output "db_instance_port" {
  description = "returns a number"
  value       = data.aws_db_instance.this.db_instance_port
}

output "db_name" {
  description = "returns a string"
  value       = data.aws_db_instance.this.db_name
}

output "db_parameter_groups" {
  description = "returns a list of string"
  value       = data.aws_db_instance.this.db_parameter_groups
}

output "db_security_groups" {
  description = "returns a list of string"
  value       = data.aws_db_instance.this.db_security_groups
}

output "db_subnet_group" {
  description = "returns a string"
  value       = data.aws_db_instance.this.db_subnet_group
}

output "enabled_cloudwatch_logs_exports" {
  description = "returns a list of string"
  value       = data.aws_db_instance.this.enabled_cloudwatch_logs_exports
}

output "endpoint" {
  description = "returns a string"
  value       = data.aws_db_instance.this.endpoint
}

output "engine" {
  description = "returns a string"
  value       = data.aws_db_instance.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_db_instance.this.engine_version
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = data.aws_db_instance.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_db_instance.this.id
}

output "iops" {
  description = "returns a number"
  value       = data.aws_db_instance.this.iops
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_db_instance.this.kms_key_id
}

output "license_model" {
  description = "returns a string"
  value       = data.aws_db_instance.this.license_model
}

output "master_username" {
  description = "returns a string"
  value       = data.aws_db_instance.this.master_username
}

output "monitoring_interval" {
  description = "returns a number"
  value       = data.aws_db_instance.this.monitoring_interval
}

output "monitoring_role_arn" {
  description = "returns a string"
  value       = data.aws_db_instance.this.monitoring_role_arn
}

output "multi_az" {
  description = "returns a bool"
  value       = data.aws_db_instance.this.multi_az
}

output "option_group_memberships" {
  description = "returns a list of string"
  value       = data.aws_db_instance.this.option_group_memberships
}

output "port" {
  description = "returns a number"
  value       = data.aws_db_instance.this.port
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = data.aws_db_instance.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = data.aws_db_instance.this.preferred_maintenance_window
}

output "publicly_accessible" {
  description = "returns a bool"
  value       = data.aws_db_instance.this.publicly_accessible
}

output "replicate_source_db" {
  description = "returns a string"
  value       = data.aws_db_instance.this.replicate_source_db
}

output "resource_id" {
  description = "returns a string"
  value       = data.aws_db_instance.this.resource_id
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = data.aws_db_instance.this.storage_encrypted
}

output "storage_type" {
  description = "returns a string"
  value       = data.aws_db_instance.this.storage_type
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_db_instance.this.tags
}

output "timezone" {
  description = "returns a string"
  value       = data.aws_db_instance.this.timezone
}

output "vpc_security_groups" {
  description = "returns a list of string"
  value       = data.aws_db_instance.this.vpc_security_groups
}

output "this" {
  value = aws_db_instance.this
}
```

[top](#index)