# aws_rds_orderable_db_instance

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_rds_orderable_db_instance" {
  source = "./modules/aws/d/aws_rds_orderable_db_instance"

  # availability_zone_group - (optional) is a type of string
  availability_zone_group = null
  # engine - (required) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # instance_class - (optional) is a type of string
  instance_class = null
  # license_model - (optional) is a type of string
  license_model = null
  # preferred_engine_versions - (optional) is a type of list of string
  preferred_engine_versions = []
  # preferred_instance_classes - (optional) is a type of list of string
  preferred_instance_classes = []
  # storage_type - (optional) is a type of string
  storage_type = null
  # supports_enhanced_monitoring - (optional) is a type of bool
  supports_enhanced_monitoring = null
  # supports_global_databases - (optional) is a type of bool
  supports_global_databases = null
  # supports_iam_database_authentication - (optional) is a type of bool
  supports_iam_database_authentication = null
  # supports_iops - (optional) is a type of bool
  supports_iops = null
  # supports_kerberos_authentication - (optional) is a type of bool
  supports_kerberos_authentication = null
  # supports_performance_insights - (optional) is a type of bool
  supports_performance_insights = null
  # supports_storage_autoscaling - (optional) is a type of bool
  supports_storage_autoscaling = null
  # supports_storage_encryption - (optional) is a type of bool
  supports_storage_encryption = null
  # vpc - (optional) is a type of bool
  vpc = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine" {
  description = "(required)"
  type        = string
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_engine_versions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "preferred_instance_classes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "supports_enhanced_monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_global_databases" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_iam_database_authentication" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_iops" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_kerberos_authentication" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_performance_insights" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_storage_autoscaling" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "supports_storage_encryption" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vpc" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_rds_orderable_db_instance" "this" {
  availability_zone_group              = var.availability_zone_group
  engine                               = var.engine
  engine_version                       = var.engine_version
  instance_class                       = var.instance_class
  license_model                        = var.license_model
  preferred_engine_versions            = var.preferred_engine_versions
  preferred_instance_classes           = var.preferred_instance_classes
  storage_type                         = var.storage_type
  supports_enhanced_monitoring         = var.supports_enhanced_monitoring
  supports_global_databases            = var.supports_global_databases
  supports_iam_database_authentication = var.supports_iam_database_authentication
  supports_iops                        = var.supports_iops
  supports_kerberos_authentication     = var.supports_kerberos_authentication
  supports_performance_insights        = var.supports_performance_insights
  supports_storage_autoscaling         = var.supports_storage_autoscaling
  supports_storage_encryption          = var.supports_storage_encryption
  vpc                                  = var.vpc
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone_group" {
  description = "returns a string"
  value       = data.aws_rds_orderable_db_instance.this.availability_zone_group
}

output "availability_zones" {
  description = "returns a list of string"
  value       = data.aws_rds_orderable_db_instance.this.availability_zones
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_rds_orderable_db_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_rds_orderable_db_instance.this.id
}

output "instance_class" {
  description = "returns a string"
  value       = data.aws_rds_orderable_db_instance.this.instance_class
}

output "license_model" {
  description = "returns a string"
  value       = data.aws_rds_orderable_db_instance.this.license_model
}

output "max_iops_per_db_instance" {
  description = "returns a number"
  value       = data.aws_rds_orderable_db_instance.this.max_iops_per_db_instance
}

output "max_iops_per_gib" {
  description = "returns a number"
  value       = data.aws_rds_orderable_db_instance.this.max_iops_per_gib
}

output "max_storage_size" {
  description = "returns a number"
  value       = data.aws_rds_orderable_db_instance.this.max_storage_size
}

output "min_iops_per_db_instance" {
  description = "returns a number"
  value       = data.aws_rds_orderable_db_instance.this.min_iops_per_db_instance
}

output "min_iops_per_gib" {
  description = "returns a number"
  value       = data.aws_rds_orderable_db_instance.this.min_iops_per_gib
}

output "min_storage_size" {
  description = "returns a number"
  value       = data.aws_rds_orderable_db_instance.this.min_storage_size
}

output "multi_az_capable" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.multi_az_capable
}

output "outpost_capable" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.outpost_capable
}

output "read_replica_capable" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.read_replica_capable
}

output "storage_type" {
  description = "returns a string"
  value       = data.aws_rds_orderable_db_instance.this.storage_type
}

output "supported_engine_modes" {
  description = "returns a list of string"
  value       = data.aws_rds_orderable_db_instance.this.supported_engine_modes
}

output "supports_enhanced_monitoring" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_enhanced_monitoring
}

output "supports_global_databases" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_global_databases
}

output "supports_iam_database_authentication" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_iam_database_authentication
}

output "supports_iops" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_iops
}

output "supports_kerberos_authentication" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_kerberos_authentication
}

output "supports_performance_insights" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_performance_insights
}

output "supports_storage_autoscaling" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_storage_autoscaling
}

output "supports_storage_encryption" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.supports_storage_encryption
}

output "vpc" {
  description = "returns a bool"
  value       = data.aws_rds_orderable_db_instance.this.vpc
}

output "this" {
  value = aws_rds_orderable_db_instance.this
}
```

[top](#index)