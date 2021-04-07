# aws_ecs_cluster

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
module "aws_ecs_cluster" {
  source = "./modules/aws/d/aws_ecs_cluster"

  # cluster_name - (required) is a type of string
  cluster_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_ecs_cluster" "this" {
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ecs_cluster.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_ecs_cluster.this.id
}

output "pending_tasks_count" {
  description = "returns a number"
  value       = data.aws_ecs_cluster.this.pending_tasks_count
}

output "registered_container_instances_count" {
  description = "returns a number"
  value       = data.aws_ecs_cluster.this.registered_container_instances_count
}

output "running_tasks_count" {
  description = "returns a number"
  value       = data.aws_ecs_cluster.this.running_tasks_count
}

output "setting" {
  description = "returns a set of object"
  value       = data.aws_ecs_cluster.this.setting
}

output "status" {
  description = "returns a string"
  value       = data.aws_ecs_cluster.this.status
}

output "this" {
  value = aws_ecs_cluster.this
}
```

[top](#index)