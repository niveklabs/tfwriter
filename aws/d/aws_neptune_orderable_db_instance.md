# aws_neptune_orderable_db_instance

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
module "aws_neptune_orderable_db_instance" {
  source = "./modules/aws/d/aws_neptune_orderable_db_instance"

  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # instance_class - (optional) is a type of string
  instance_class = null
  # license_model - (optional) is a type of string
  license_model = null
  # preferred_instance_classes - (optional) is a type of list of string
  preferred_instance_classes = []
  # vpc - (optional) is a type of bool
  vpc = null
}
```

[top](#index)

### Variables

```terraform
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

variable "preferred_instance_classes" {
  description = "(optional)"
  type        = list(string)
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
data "aws_neptune_orderable_db_instance" "this" {
  engine                     = var.engine
  engine_version             = var.engine_version
  instance_class             = var.instance_class
  license_model              = var.license_model
  preferred_instance_classes = var.preferred_instance_classes
  vpc                        = var.vpc
}
```

[top](#index)

### Outputs

```terraform
output "availability_zones" {
  description = "returns a list of string"
  value       = data.aws_neptune_orderable_db_instance.this.availability_zones
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_neptune_orderable_db_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_neptune_orderable_db_instance.this.id
}

output "instance_class" {
  description = "returns a string"
  value       = data.aws_neptune_orderable_db_instance.this.instance_class
}

output "max_iops_per_db_instance" {
  description = "returns a number"
  value       = data.aws_neptune_orderable_db_instance.this.max_iops_per_db_instance
}

output "max_iops_per_gib" {
  description = "returns a number"
  value       = data.aws_neptune_orderable_db_instance.this.max_iops_per_gib
}

output "max_storage_size" {
  description = "returns a number"
  value       = data.aws_neptune_orderable_db_instance.this.max_storage_size
}

output "min_iops_per_db_instance" {
  description = "returns a number"
  value       = data.aws_neptune_orderable_db_instance.this.min_iops_per_db_instance
}

output "min_iops_per_gib" {
  description = "returns a number"
  value       = data.aws_neptune_orderable_db_instance.this.min_iops_per_gib
}

output "min_storage_size" {
  description = "returns a number"
  value       = data.aws_neptune_orderable_db_instance.this.min_storage_size
}

output "multi_az_capable" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.multi_az_capable
}

output "read_replica_capable" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.read_replica_capable
}

output "storage_type" {
  description = "returns a string"
  value       = data.aws_neptune_orderable_db_instance.this.storage_type
}

output "supports_enhanced_monitoring" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.supports_enhanced_monitoring
}

output "supports_iam_database_authentication" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.supports_iam_database_authentication
}

output "supports_iops" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.supports_iops
}

output "supports_performance_insights" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.supports_performance_insights
}

output "supports_storage_encryption" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.supports_storage_encryption
}

output "vpc" {
  description = "returns a bool"
  value       = data.aws_neptune_orderable_db_instance.this.vpc
}

output "this" {
  value = aws_neptune_orderable_db_instance.this
}
```

[top](#index)