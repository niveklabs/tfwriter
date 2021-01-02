# aws_elasticache_cluster

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_elasticache_cluster" {
  source = "./modules/aws/r/aws_elasticache_cluster"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # az_mode - (optional) is a type of string
  az_mode = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # maintenance_window - (optional) is a type of string
  maintenance_window = null
  # node_type - (optional) is a type of string
  node_type = null
  # notification_topic_arn - (optional) is a type of string
  notification_topic_arn = null
  # num_cache_nodes - (optional) is a type of number
  num_cache_nodes = null
  # parameter_group_name - (optional) is a type of string
  parameter_group_name = null
  # port - (optional) is a type of number
  port = null
  # preferred_availability_zones - (optional) is a type of list of string
  preferred_availability_zones = []
  # replication_group_id - (optional) is a type of string
  replication_group_id = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # security_group_names - (optional) is a type of set of string
  security_group_names = []
  # snapshot_arns - (optional) is a type of set of string
  snapshot_arns = []
  # snapshot_name - (optional) is a type of string
  snapshot_name = null
  # snapshot_retention_limit - (optional) is a type of number
  snapshot_retention_limit = null
  # snapshot_window - (optional) is a type of string
  snapshot_window = null
  # subnet_group_name - (optional) is a type of string
  subnet_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "apply_immediately" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "az_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
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

variable "maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_cache_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preferred_availability_zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "replication_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "security_group_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "snapshot_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "snapshot_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_retention_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snapshot_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_group_name" {
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

### Resource

```terraform
resource "aws_elasticache_cluster" "this" {
  apply_immediately            = var.apply_immediately
  availability_zone            = var.availability_zone
  az_mode                      = var.az_mode
  cluster_id                   = var.cluster_id
  engine                       = var.engine
  engine_version               = var.engine_version
  maintenance_window           = var.maintenance_window
  node_type                    = var.node_type
  notification_topic_arn       = var.notification_topic_arn
  num_cache_nodes              = var.num_cache_nodes
  parameter_group_name         = var.parameter_group_name
  port                         = var.port
  preferred_availability_zones = var.preferred_availability_zones
  replication_group_id         = var.replication_group_id
  security_group_ids           = var.security_group_ids
  security_group_names         = var.security_group_names
  snapshot_arns                = var.snapshot_arns
  snapshot_name                = var.snapshot_name
  snapshot_retention_limit     = var.snapshot_retention_limit
  snapshot_window              = var.snapshot_window
  subnet_group_name            = var.subnet_group_name
  tags                         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "apply_immediately" {
  description = "returns a bool"
  value       = aws_elasticache_cluster.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.availability_zone
}

output "az_mode" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.az_mode
}

output "cache_nodes" {
  description = "returns a list of object"
  value       = aws_elasticache_cluster.this.cache_nodes
}

output "cluster_address" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.cluster_address
}

output "configuration_endpoint" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.configuration_endpoint
}

output "engine" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.id
}

output "maintenance_window" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.maintenance_window
}

output "node_type" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.node_type
}

output "num_cache_nodes" {
  description = "returns a number"
  value       = aws_elasticache_cluster.this.num_cache_nodes
}

output "parameter_group_name" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.parameter_group_name
}

output "port" {
  description = "returns a number"
  value       = aws_elasticache_cluster.this.port
}

output "replication_group_id" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.replication_group_id
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = aws_elasticache_cluster.this.security_group_ids
}

output "security_group_names" {
  description = "returns a set of string"
  value       = aws_elasticache_cluster.this.security_group_names
}

output "snapshot_window" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.snapshot_window
}

output "subnet_group_name" {
  description = "returns a string"
  value       = aws_elasticache_cluster.this.subnet_group_name
}

output "this" {
  value = aws_elasticache_cluster.this
}
```

[top](#index)