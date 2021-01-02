# aws_dax_cluster

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
module "aws_dax_cluster" {
  source = "./modules/aws/r/aws_dax_cluster"

  # availability_zones - (optional) is a type of set of string
  availability_zones = []
  # cluster_name - (required) is a type of string
  cluster_name = null
  # description - (optional) is a type of string
  description = null
  # iam_role_arn - (required) is a type of string
  iam_role_arn = null
  # maintenance_window - (optional) is a type of string
  maintenance_window = null
  # node_type - (required) is a type of string
  node_type = null
  # notification_topic_arn - (optional) is a type of string
  notification_topic_arn = null
  # parameter_group_name - (optional) is a type of string
  parameter_group_name = null
  # replication_factor - (required) is a type of number
  replication_factor = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # subnet_group_name - (optional) is a type of string
  subnet_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  server_side_encryption = [{
    enabled = null
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
variable "availability_zones" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_role_arn" {
  description = "(required)"
  type        = string
}

variable "maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(required)"
  type        = string
}

variable "notification_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replication_factor" {
  description = "(required)"
  type        = number
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
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

variable "server_side_encryption" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
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
resource "aws_dax_cluster" "this" {
  availability_zones     = var.availability_zones
  cluster_name           = var.cluster_name
  description            = var.description
  iam_role_arn           = var.iam_role_arn
  maintenance_window     = var.maintenance_window
  node_type              = var.node_type
  notification_topic_arn = var.notification_topic_arn
  parameter_group_name   = var.parameter_group_name
  replication_factor     = var.replication_factor
  security_group_ids     = var.security_group_ids
  subnet_group_name      = var.subnet_group_name
  tags                   = var.tags

  dynamic "server_side_encryption" {
    for_each = var.server_side_encryption
    content {
      enabled = server_side_encryption.value["enabled"]
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
output "arn" {
  description = "returns a string"
  value       = aws_dax_cluster.this.arn
}

output "cluster_address" {
  description = "returns a string"
  value       = aws_dax_cluster.this.cluster_address
}

output "configuration_endpoint" {
  description = "returns a string"
  value       = aws_dax_cluster.this.configuration_endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_dax_cluster.this.id
}

output "maintenance_window" {
  description = "returns a string"
  value       = aws_dax_cluster.this.maintenance_window
}

output "nodes" {
  description = "returns a list of object"
  value       = aws_dax_cluster.this.nodes
}

output "parameter_group_name" {
  description = "returns a string"
  value       = aws_dax_cluster.this.parameter_group_name
}

output "port" {
  description = "returns a number"
  value       = aws_dax_cluster.this.port
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = aws_dax_cluster.this.security_group_ids
}

output "subnet_group_name" {
  description = "returns a string"
  value       = aws_dax_cluster.this.subnet_group_name
}

output "this" {
  value = aws_dax_cluster.this
}
```

[top](#index)