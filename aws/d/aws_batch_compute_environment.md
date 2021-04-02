# aws_batch_compute_environment

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
module "aws_batch_compute_environment" {
  source = "./modules/aws/d/aws_batch_compute_environment"

  # compute_environment_name - (required) is a type of string
  compute_environment_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "compute_environment_name" {
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
data "aws_batch_compute_environment" "this" {
  compute_environment_name = var.compute_environment_name
  tags                     = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.arn
}

output "ecs_cluster_arn" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.ecs_cluster_arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.id
}

output "service_role" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.service_role
}

output "state" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.state
}

output "status" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.status
}

output "status_reason" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.status_reason
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_batch_compute_environment.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.aws_batch_compute_environment.this.type
}

output "this" {
  value = aws_batch_compute_environment.this
}
```

[top](#index)