# aws_rds_engine_version

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
module "aws_rds_engine_version" {
  source = "./modules/aws/d/aws_rds_engine_version"

  # engine - (required) is a type of string
  engine = null
  # parameter_group_family - (optional) is a type of string
  parameter_group_family = null
  # preferred_versions - (optional) is a type of list of string
  preferred_versions = []
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "engine" {
  description = "(required)"
  type        = string
}

variable "parameter_group_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_versions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_rds_engine_version" "this" {
  engine                 = var.engine
  parameter_group_family = var.parameter_group_family
  preferred_versions     = var.preferred_versions
  version                = var.version
}
```

[top](#index)

### Outputs

```terraform
output "default_character_set" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.default_character_set
}

output "engine_description" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.engine_description
}

output "exportable_log_types" {
  description = "returns a set of string"
  value       = data.aws_rds_engine_version.this.exportable_log_types
}

output "id" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.id
}

output "parameter_group_family" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.parameter_group_family
}

output "status" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.status
}

output "supported_character_sets" {
  description = "returns a set of string"
  value       = data.aws_rds_engine_version.this.supported_character_sets
}

output "supported_feature_names" {
  description = "returns a set of string"
  value       = data.aws_rds_engine_version.this.supported_feature_names
}

output "supported_modes" {
  description = "returns a set of string"
  value       = data.aws_rds_engine_version.this.supported_modes
}

output "supported_timezones" {
  description = "returns a set of string"
  value       = data.aws_rds_engine_version.this.supported_timezones
}

output "supports_global_databases" {
  description = "returns a bool"
  value       = data.aws_rds_engine_version.this.supports_global_databases
}

output "supports_log_exports_to_cloudwatch" {
  description = "returns a bool"
  value       = data.aws_rds_engine_version.this.supports_log_exports_to_cloudwatch
}

output "supports_parallel_query" {
  description = "returns a bool"
  value       = data.aws_rds_engine_version.this.supports_parallel_query
}

output "supports_read_replica" {
  description = "returns a bool"
  value       = data.aws_rds_engine_version.this.supports_read_replica
}

output "valid_upgrade_targets" {
  description = "returns a set of string"
  value       = data.aws_rds_engine_version.this.valid_upgrade_targets
}

output "version" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.version
}

output "version_description" {
  description = "returns a string"
  value       = data.aws_rds_engine_version.this.version_description
}

output "this" {
  value = aws_rds_engine_version.this
}
```

[top](#index)