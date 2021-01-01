# aws_ecs_task_definition

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
module "aws_ecs_task_definition" {
  source = "./modules/aws/d/aws_ecs_task_definition"

  # task_definition - (required) is a type of string
  task_definition = null
}
```

[top](#index)

### Variables

```hcl
variable "task_definition" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_ecs_task_definition" "this" {
  task_definition = var.task_definition
}
```

[top](#index)

### Outputs

```hcl
output "family" {
  description = "returns a string"
  value       = data.aws_ecs_task_definition.this.family
}

output "id" {
  description = "returns a string"
  value       = data.aws_ecs_task_definition.this.id
}

output "network_mode" {
  description = "returns a string"
  value       = data.aws_ecs_task_definition.this.network_mode
}

output "revision" {
  description = "returns a number"
  value       = data.aws_ecs_task_definition.this.revision
}

output "status" {
  description = "returns a string"
  value       = data.aws_ecs_task_definition.this.status
}

output "task_role_arn" {
  description = "returns a string"
  value       = data.aws_ecs_task_definition.this.task_role_arn
}

output "this" {
  value = aws_ecs_task_definition.this
}
```

[top](#index)