# aws_ecs_service

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ecs_service" {
  source = "./modules/aws/d/aws_ecs_service"

  # cluster_arn - (required) is a type of string
  cluster_arn = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_arn" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_ecs_service" "this" {
  cluster_arn  = var.cluster_arn
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ecs_service.this.arn
}

output "desired_count" {
  description = "returns a number"
  value       = data.aws_ecs_service.this.desired_count
}

output "id" {
  description = "returns a string"
  value       = data.aws_ecs_service.this.id
}

output "launch_type" {
  description = "returns a string"
  value       = data.aws_ecs_service.this.launch_type
}

output "scheduling_strategy" {
  description = "returns a string"
  value       = data.aws_ecs_service.this.scheduling_strategy
}

output "task_definition" {
  description = "returns a string"
  value       = data.aws_ecs_service.this.task_definition
}

output "this" {
  value = aws_ecs_service.this
}
```

[top](#index)