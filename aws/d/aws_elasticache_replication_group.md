# aws_elasticache_replication_group

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_elasticache_replication_group" {
  source = "./modules/aws/d/aws_elasticache_replication_group"

  # replication_group_id - (required) is a type of string
  replication_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "replication_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_elasticache_replication_group" "this" {
  replication_group_id = var.replication_group_id
}
```

[top](#index)

### Outputs

```terraform
output "auth_token_enabled" {
  description = "returns a bool"
  value       = data.aws_elasticache_replication_group.this.auth_token_enabled
}

output "automatic_failover_enabled" {
  description = "returns a bool"
  value       = data.aws_elasticache_replication_group.this.automatic_failover_enabled
}

output "configuration_endpoint_address" {
  description = "returns a string"
  value       = data.aws_elasticache_replication_group.this.configuration_endpoint_address
}

output "id" {
  description = "returns a string"
  value       = data.aws_elasticache_replication_group.this.id
}

output "member_clusters" {
  description = "returns a set of string"
  value       = data.aws_elasticache_replication_group.this.member_clusters
}

output "node_type" {
  description = "returns a string"
  value       = data.aws_elasticache_replication_group.this.node_type
}

output "number_cache_clusters" {
  description = "returns a number"
  value       = data.aws_elasticache_replication_group.this.number_cache_clusters
}

output "port" {
  description = "returns a number"
  value       = data.aws_elasticache_replication_group.this.port
}

output "primary_endpoint_address" {
  description = "returns a string"
  value       = data.aws_elasticache_replication_group.this.primary_endpoint_address
}

output "replication_group_description" {
  description = "returns a string"
  value       = data.aws_elasticache_replication_group.this.replication_group_description
}

output "snapshot_retention_limit" {
  description = "returns a number"
  value       = data.aws_elasticache_replication_group.this.snapshot_retention_limit
}

output "snapshot_window" {
  description = "returns a string"
  value       = data.aws_elasticache_replication_group.this.snapshot_window
}

output "this" {
  value = aws_elasticache_replication_group.this
}
```

[top](#index)