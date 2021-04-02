# aws_batch_job_queue

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
module "aws_batch_job_queue" {
  source = "./modules/aws/d/aws_batch_job_queue"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "aws_batch_job_queue" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_batch_job_queue.this.arn
}

output "compute_environment_order" {
  description = "returns a list of object"
  value       = data.aws_batch_job_queue.this.compute_environment_order
}

output "id" {
  description = "returns a string"
  value       = data.aws_batch_job_queue.this.id
}

output "priority" {
  description = "returns a number"
  value       = data.aws_batch_job_queue.this.priority
}

output "state" {
  description = "returns a string"
  value       = data.aws_batch_job_queue.this.state
}

output "status" {
  description = "returns a string"
  value       = data.aws_batch_job_queue.this.status
}

output "status_reason" {
  description = "returns a string"
  value       = data.aws_batch_job_queue.this.status_reason
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_batch_job_queue.this.tags
}

output "this" {
  value = aws_batch_job_queue.this
}
```

[top](#index)