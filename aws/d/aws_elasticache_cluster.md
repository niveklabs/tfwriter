# aws_elasticache_cluster

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
module "aws_elasticache_cluster" {
  source = "./modules/aws/d/aws_elasticache_cluster"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_elasticache_cluster" "this" {
  cluster_id = var.cluster_id
  tags       = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.availability_zone
}

output "cache_nodes" {
  description = "returns a list of object"
  value       = data.aws_elasticache_cluster.this.cache_nodes
}

output "cluster_address" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.cluster_address
}

output "configuration_endpoint" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.configuration_endpoint
}

output "engine" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.id
}

output "maintenance_window" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.maintenance_window
}

output "node_type" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.node_type
}

output "notification_topic_arn" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.notification_topic_arn
}

output "num_cache_nodes" {
  description = "returns a number"
  value       = data.aws_elasticache_cluster.this.num_cache_nodes
}

output "parameter_group_name" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.parameter_group_name
}

output "port" {
  description = "returns a number"
  value       = data.aws_elasticache_cluster.this.port
}

output "replication_group_id" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.replication_group_id
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = data.aws_elasticache_cluster.this.security_group_ids
}

output "security_group_names" {
  description = "returns a set of string"
  value       = data.aws_elasticache_cluster.this.security_group_names
}

output "snapshot_retention_limit" {
  description = "returns a number"
  value       = data.aws_elasticache_cluster.this.snapshot_retention_limit
}

output "snapshot_window" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.snapshot_window
}

output "subnet_group_name" {
  description = "returns a string"
  value       = data.aws_elasticache_cluster.this.subnet_group_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_elasticache_cluster.this.tags
}

output "this" {
  value = aws_elasticache_cluster.this
}
```

[top](#index)