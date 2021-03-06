# aws_batch_job_queue

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_batch_job_queue" {
  source = "./modules/aws/r/aws_batch_job_queue"

  # compute_environments - (required) is a type of list of string
  compute_environments = []
  # name - (required) is a type of string
  name = null
  # priority - (required) is a type of number
  priority = null
  # state - (required) is a type of string
  state = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "compute_environments" {
  description = "(required)"
  type        = list(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "state" {
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

### Resource

```terraform
resource "aws_batch_job_queue" "this" {
  # compute_environments - (required) is a type of list of string
  compute_environments = var.compute_environments
  # name - (required) is a type of string
  name = var.name
  # priority - (required) is a type of number
  priority = var.priority
  # state - (required) is a type of string
  state = var.state
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_batch_job_queue.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_batch_job_queue.this.id
}

output "this" {
  value = aws_batch_job_queue.this
}
```

[top](#index)