# aws_db_snapshot

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
module "aws_db_snapshot" {
  source = "./modules/aws/d/aws_db_snapshot"

  # db_instance_identifier - (optional) is a type of string
  db_instance_identifier = null
  # db_snapshot_identifier - (optional) is a type of string
  db_snapshot_identifier = null
  # include_public - (optional) is a type of bool
  include_public = null
  # include_shared - (optional) is a type of bool
  include_shared = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # snapshot_type - (optional) is a type of string
  snapshot_type = null
}
```

[top](#index)

### Variables

```terraform
variable "db_instance_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_snapshot_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "include_shared" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "snapshot_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_db_snapshot" "this" {
  # db_instance_identifier - (optional) is a type of string
  db_instance_identifier = var.db_instance_identifier
  # db_snapshot_identifier - (optional) is a type of string
  db_snapshot_identifier = var.db_snapshot_identifier
  # include_public - (optional) is a type of bool
  include_public = var.include_public
  # include_shared - (optional) is a type of bool
  include_shared = var.include_shared
  # most_recent - (optional) is a type of bool
  most_recent = var.most_recent
  # snapshot_type - (optional) is a type of string
  snapshot_type = var.snapshot_type
}
```

[top](#index)

### Outputs

```terraform
output "allocated_storage" {
  description = "returns a number"
  value       = data.aws_db_snapshot.this.allocated_storage
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.availability_zone
}

output "db_snapshot_arn" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.db_snapshot_arn
}

output "encrypted" {
  description = "returns a bool"
  value       = data.aws_db_snapshot.this.encrypted
}

output "engine" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.id
}

output "iops" {
  description = "returns a number"
  value       = data.aws_db_snapshot.this.iops
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.kms_key_id
}

output "license_model" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.license_model
}

output "option_group_name" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.option_group_name
}

output "port" {
  description = "returns a number"
  value       = data.aws_db_snapshot.this.port
}

output "snapshot_create_time" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.snapshot_create_time
}

output "source_db_snapshot_identifier" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.source_db_snapshot_identifier
}

output "source_region" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.source_region
}

output "status" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.status
}

output "storage_type" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.storage_type
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_db_snapshot.this.vpc_id
}

output "this" {
  value = aws_db_snapshot.this
}
```

[top](#index)