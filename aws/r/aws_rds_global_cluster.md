# aws_rds_global_cluster

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
module "aws_rds_global_cluster" {
  source = "./modules/aws/r/aws_rds_global_cluster"

  # database_name - (optional) is a type of string
  database_name = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # global_cluster_identifier - (required) is a type of string
  global_cluster_identifier = null
  # source_db_cluster_identifier - (optional) is a type of string
  source_db_cluster_identifier = null
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = null
}
```

[top](#index)

### Variables

```terraform
variable "database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
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

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "global_cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "source_db_cluster_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_rds_global_cluster" "this" {
  # database_name - (optional) is a type of string
  database_name = var.database_name
  # deletion_protection - (optional) is a type of bool
  deletion_protection = var.deletion_protection
  # engine - (optional) is a type of string
  engine = var.engine
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # global_cluster_identifier - (required) is a type of string
  global_cluster_identifier = var.global_cluster_identifier
  # source_db_cluster_identifier - (optional) is a type of string
  source_db_cluster_identifier = var.source_db_cluster_identifier
  # storage_encrypted - (optional) is a type of bool
  storage_encrypted = var.storage_encrypted
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_rds_global_cluster.this.arn
}

output "engine" {
  description = "returns a string"
  value       = aws_rds_global_cluster.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = aws_rds_global_cluster.this.engine_version
}

output "global_cluster_members" {
  description = "returns a set of object"
  value       = aws_rds_global_cluster.this.global_cluster_members
}

output "global_cluster_resource_id" {
  description = "returns a string"
  value       = aws_rds_global_cluster.this.global_cluster_resource_id
}

output "id" {
  description = "returns a string"
  value       = aws_rds_global_cluster.this.id
}

output "source_db_cluster_identifier" {
  description = "returns a string"
  value       = aws_rds_global_cluster.this.source_db_cluster_identifier
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = aws_rds_global_cluster.this.storage_encrypted
}

output "this" {
  value = aws_rds_global_cluster.this
}
```

[top](#index)