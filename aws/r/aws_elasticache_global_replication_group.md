# aws_elasticache_global_replication_group

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
module "aws_elasticache_global_replication_group" {
  source = "./modules/aws/r/aws_elasticache_global_replication_group"

  # global_replication_group_description - (optional) is a type of string
  global_replication_group_description = null
  # global_replication_group_id_suffix - (required) is a type of string
  global_replication_group_id_suffix = null
  # primary_replication_group_id - (required) is a type of string
  primary_replication_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "global_replication_group_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global_replication_group_id_suffix" {
  description = "(required)"
  type        = string
}

variable "primary_replication_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_elasticache_global_replication_group" "this" {
  global_replication_group_description = var.global_replication_group_description
  global_replication_group_id_suffix   = var.global_replication_group_id_suffix
  primary_replication_group_id         = var.primary_replication_group_id
}
```

[top](#index)

### Outputs

```terraform
output "actual_engine_version" {
  description = "returns a string"
  value       = aws_elasticache_global_replication_group.this.actual_engine_version
}

output "arn" {
  description = "returns a string"
  value       = aws_elasticache_global_replication_group.this.arn
}

output "at_rest_encryption_enabled" {
  description = "returns a bool"
  value       = aws_elasticache_global_replication_group.this.at_rest_encryption_enabled
}

output "auth_token_enabled" {
  description = "returns a bool"
  value       = aws_elasticache_global_replication_group.this.auth_token_enabled
}

output "cache_node_type" {
  description = "returns a string"
  value       = aws_elasticache_global_replication_group.this.cache_node_type
}

output "cluster_enabled" {
  description = "returns a bool"
  value       = aws_elasticache_global_replication_group.this.cluster_enabled
}

output "engine" {
  description = "returns a string"
  value       = aws_elasticache_global_replication_group.this.engine
}

output "global_replication_group_id" {
  description = "returns a string"
  value       = aws_elasticache_global_replication_group.this.global_replication_group_id
}

output "id" {
  description = "returns a string"
  value       = aws_elasticache_global_replication_group.this.id
}

output "transit_encryption_enabled" {
  description = "returns a bool"
  value       = aws_elasticache_global_replication_group.this.transit_encryption_enabled
}

output "this" {
  value = aws_elasticache_global_replication_group.this
}
```

[top](#index)