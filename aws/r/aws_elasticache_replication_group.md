# aws_elasticache_replication_group

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
module "aws_elasticache_replication_group" {
  source = "./modules/aws/r/aws_elasticache_replication_group"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # at_rest_encryption_enabled - (optional) is a type of bool
  at_rest_encryption_enabled = null
  # auth_token - (optional) is a type of string
  auth_token = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # automatic_failover_enabled - (optional) is a type of bool
  automatic_failover_enabled = null
  # availability_zones - (optional) is a type of set of string
  availability_zones = []
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # maintenance_window - (optional) is a type of string
  maintenance_window = null
  # node_type - (optional) is a type of string
  node_type = null
  # notification_topic_arn - (optional) is a type of string
  notification_topic_arn = null
  # number_cache_clusters - (optional) is a type of number
  number_cache_clusters = null
  # parameter_group_name - (optional) is a type of string
  parameter_group_name = null
  # port - (optional) is a type of number
  port = null
  # replication_group_description - (required) is a type of string
  replication_group_description = null
  # replication_group_id - (required) is a type of string
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
  # transit_encryption_enabled - (optional) is a type of bool
  transit_encryption_enabled = null

  cluster_mode = [{
    num_node_groups         = null
    replicas_per_node_group = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
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

variable "at_rest_encryption_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auth_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_minor_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "automatic_failover_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zones" {
  description = "(optional)"
  type        = set(string)
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

variable "kms_key_id" {
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

variable "number_cache_clusters" {
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

variable "replication_group_description" {
  description = "(required)"
  type        = string
}

variable "replication_group_id" {
  description = "(required)"
  type        = string
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

variable "transit_encryption_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cluster_mode" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      num_node_groups         = number
      replicas_per_node_group = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_elasticache_replication_group" "this" {
  apply_immediately             = var.apply_immediately
  at_rest_encryption_enabled    = var.at_rest_encryption_enabled
  auth_token                    = var.auth_token
  auto_minor_version_upgrade    = var.auto_minor_version_upgrade
  automatic_failover_enabled    = var.automatic_failover_enabled
  availability_zones            = var.availability_zones
  engine                        = var.engine
  engine_version                = var.engine_version
  kms_key_id                    = var.kms_key_id
  maintenance_window            = var.maintenance_window
  node_type                     = var.node_type
  notification_topic_arn        = var.notification_topic_arn
  number_cache_clusters         = var.number_cache_clusters
  parameter_group_name          = var.parameter_group_name
  port                          = var.port
  replication_group_description = var.replication_group_description
  replication_group_id          = var.replication_group_id
  security_group_ids            = var.security_group_ids
  security_group_names          = var.security_group_names
  snapshot_arns                 = var.snapshot_arns
  snapshot_name                 = var.snapshot_name
  snapshot_retention_limit      = var.snapshot_retention_limit
  snapshot_window               = var.snapshot_window
  subnet_group_name             = var.subnet_group_name
  tags                          = var.tags
  transit_encryption_enabled    = var.transit_encryption_enabled

  dynamic "cluster_mode" {
    for_each = var.cluster_mode
    content {
      num_node_groups         = cluster_mode.value["num_node_groups"]
      replicas_per_node_group = cluster_mode.value["replicas_per_node_group"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "apply_immediately" {
  description = "returns a bool"
  value       = aws_elasticache_replication_group.this.apply_immediately
}

output "configuration_endpoint_address" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.configuration_endpoint_address
}

output "engine_version" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.id
}

output "maintenance_window" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.maintenance_window
}

output "member_clusters" {
  description = "returns a set of string"
  value       = aws_elasticache_replication_group.this.member_clusters
}

output "node_type" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.node_type
}

output "number_cache_clusters" {
  description = "returns a number"
  value       = aws_elasticache_replication_group.this.number_cache_clusters
}

output "parameter_group_name" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.parameter_group_name
}

output "primary_endpoint_address" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.primary_endpoint_address
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = aws_elasticache_replication_group.this.security_group_ids
}

output "security_group_names" {
  description = "returns a set of string"
  value       = aws_elasticache_replication_group.this.security_group_names
}

output "snapshot_window" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.snapshot_window
}

output "subnet_group_name" {
  description = "returns a string"
  value       = aws_elasticache_replication_group.this.subnet_group_name
}

output "this" {
  value = aws_elasticache_replication_group.this
}
```

[top](#index)