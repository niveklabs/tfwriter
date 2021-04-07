# aws_rds_cluster_instance

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
module "aws_rds_cluster_instance" {
  source = "./modules/aws/r/aws_rds_cluster_instance"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # ca_cert_identifier - (optional) is a type of string
  ca_cert_identifier = null
  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # copy_tags_to_snapshot - (optional) is a type of bool
  copy_tags_to_snapshot = null
  # db_parameter_group_name - (optional) is a type of string
  db_parameter_group_name = null
  # db_subnet_group_name - (optional) is a type of string
  db_subnet_group_name = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # identifier - (optional) is a type of string
  identifier = null
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = null
  # instance_class - (required) is a type of string
  instance_class = null
  # monitoring_interval - (optional) is a type of number
  monitoring_interval = null
  # monitoring_role_arn - (optional) is a type of string
  monitoring_role_arn = null
  # performance_insights_enabled - (optional) is a type of bool
  performance_insights_enabled = null
  # performance_insights_kms_key_id - (optional) is a type of string
  performance_insights_kms_key_id = null
  # preferred_backup_window - (optional) is a type of string
  preferred_backup_window = null
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = null
  # promotion_tier - (optional) is a type of number
  promotion_tier = null
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "ca_cert_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "copy_tags_to_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "db_parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_subnet_group_name" {
  description = "(optional)"
  type        = string
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

variable "promotion_tier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "publicly_accessible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "aws_rds_cluster_instance" "this" {
  # apply_immediately - (optional) is a type of bool
  apply_immediately = var.apply_immediately
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = var.auto_minor_version_upgrade
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # ca_cert_identifier - (optional) is a type of string
  ca_cert_identifier = var.ca_cert_identifier
  # cluster_identifier - (required) is a type of string
  cluster_identifier = var.cluster_identifier
  # copy_tags_to_snapshot - (optional) is a type of bool
  copy_tags_to_snapshot = var.copy_tags_to_snapshot
  # db_parameter_group_name - (optional) is a type of string
  db_parameter_group_name = var.db_parameter_group_name
  # db_subnet_group_name - (optional) is a type of string
  db_subnet_group_name = var.db_subnet_group_name
  # engine - (optional) is a type of string
  engine = var.engine
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # identifier - (optional) is a type of string
  identifier = var.identifier
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = var.identifier_prefix
  # instance_class - (required) is a type of string
  instance_class = var.instance_class
  # monitoring_interval - (optional) is a type of number
  monitoring_interval = var.monitoring_interval
  # monitoring_role_arn - (optional) is a type of string
  monitoring_role_arn = var.monitoring_role_arn
  # performance_insights_enabled - (optional) is a type of bool
  performance_insights_enabled = var.performance_insights_enabled
  # performance_insights_kms_key_id - (optional) is a type of string
  performance_insights_kms_key_id = var.performance_insights_kms_key_id
  # preferred_backup_window - (optional) is a type of string
  preferred_backup_window = var.preferred_backup_window
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = var.preferred_maintenance_window
  # promotion_tier - (optional) is a type of number
  promotion_tier = var.promotion_tier
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = var.publicly_accessible
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = aws_rds_cluster_instance.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.availability_zone
}

output "ca_cert_identifier" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.ca_cert_identifier
}

output "db_parameter_group_name" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.db_parameter_group_name
}

output "db_subnet_group_name" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.db_subnet_group_name
}

output "dbi_resource_id" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.dbi_resource_id
}

output "endpoint" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.endpoint
}

output "engine_version" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.id
}

output "identifier" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.identifier
}

output "identifier_prefix" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.identifier_prefix
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.kms_key_id
}

output "monitoring_role_arn" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.monitoring_role_arn
}

output "performance_insights_enabled" {
  description = "returns a bool"
  value       = aws_rds_cluster_instance.this.performance_insights_enabled
}

output "performance_insights_kms_key_id" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.performance_insights_kms_key_id
}

output "port" {
  description = "returns a number"
  value       = aws_rds_cluster_instance.this.port
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_rds_cluster_instance.this.preferred_maintenance_window
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = aws_rds_cluster_instance.this.storage_encrypted
}

output "writer" {
  description = "returns a bool"
  value       = aws_rds_cluster_instance.this.writer
}

output "this" {
  value = aws_rds_cluster_instance.this
}
```

[top](#index)