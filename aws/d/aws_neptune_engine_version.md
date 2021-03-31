# aws_neptune_engine_version

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
module "aws_neptune_engine_version" {
  source = "./modules/aws/d/aws_neptune_engine_version"

  # engine - (optional) is a type of string
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
  description = "(optional)"
  type        = string
  default     = null
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
data "aws_neptune_engine_version" "this" {
  engine                 = var.engine
  parameter_group_family = var.parameter_group_family
  preferred_versions     = var.preferred_versions
  version                = var.version
}
```

[top](#index)

### Outputs

```terraform
output "engine_description" {
  description = "returns a string"
  value       = data.aws_neptune_engine_version.this.engine_description
}

output "exportable_log_types" {
  description = "returns a list of string"
  value       = data.aws_neptune_engine_version.this.exportable_log_types
}

output "id" {
  description = "returns a string"
  value       = data.aws_neptune_engine_version.this.id
}

output "parameter_group_family" {
  description = "returns a string"
  value       = data.aws_neptune_engine_version.this.parameter_group_family
}

output "supported_timezones" {
  description = "returns a set of string"
  value       = data.aws_neptune_engine_version.this.supported_timezones
}

output "supports_log_exports_to_cloudwatch" {
  description = "returns a bool"
  value       = data.aws_neptune_engine_version.this.supports_log_exports_to_cloudwatch
}

output "supports_read_replica" {
  description = "returns a bool"
  value       = data.aws_neptune_engine_version.this.supports_read_replica
}

output "valid_upgrade_targets" {
  description = "returns a set of string"
  value       = data.aws_neptune_engine_version.this.valid_upgrade_targets
}

output "version" {
  description = "returns a string"
  value       = data.aws_neptune_engine_version.this.version
}

output "version_description" {
  description = "returns a string"
  value       = data.aws_neptune_engine_version.this.version_description
}

output "this" {
  value = aws_neptune_engine_version.this
}
```

[top](#index)