# aws_db_cluster_snapshot

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
module "aws_db_cluster_snapshot" {
  source = "./modules/aws/d/aws_db_cluster_snapshot"

  # db_cluster_identifier - (optional) is a type of string
  db_cluster_identifier = null
  # db_cluster_snapshot_identifier - (optional) is a type of string
  db_cluster_snapshot_identifier = null
  # include_public - (optional) is a type of bool
  include_public = null
  # include_shared - (optional) is a type of bool
  include_shared = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # snapshot_type - (optional) is a type of string
  snapshot_type = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "db_cluster_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_snapshot_identifier" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_db_cluster_snapshot" "this" {
  db_cluster_identifier          = var.db_cluster_identifier
  db_cluster_snapshot_identifier = var.db_cluster_snapshot_identifier
  include_public                 = var.include_public
  include_shared                 = var.include_shared
  most_recent                    = var.most_recent
  snapshot_type                  = var.snapshot_type
  tags                           = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "allocated_storage" {
  description = "returns a number"
  value       = data.aws_db_cluster_snapshot.this.allocated_storage
}

output "availability_zones" {
  description = "returns a list of string"
  value       = data.aws_db_cluster_snapshot.this.availability_zones
}

output "db_cluster_snapshot_arn" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.db_cluster_snapshot_arn
}

output "engine" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.kms_key_id
}

output "license_model" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.license_model
}

output "port" {
  description = "returns a number"
  value       = data.aws_db_cluster_snapshot.this.port
}

output "snapshot_create_time" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.snapshot_create_time
}

output "source_db_cluster_snapshot_arn" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.source_db_cluster_snapshot_arn
}

output "status" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.status
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = data.aws_db_cluster_snapshot.this.storage_encrypted
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_db_cluster_snapshot.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_db_cluster_snapshot.this.vpc_id
}

output "this" {
  value = aws_db_cluster_snapshot.this
}
```

[top](#index)