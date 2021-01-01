# aws_batch_job_queue

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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

```hcl
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

```hcl
resource "aws_batch_job_queue" "this" {
  compute_environments = var.compute_environments
  name                 = var.name
  priority             = var.priority
  state                = var.state
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```hcl
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