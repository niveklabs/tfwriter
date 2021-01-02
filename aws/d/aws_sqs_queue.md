# aws_sqs_queue

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_sqs_queue" {
  source = "./modules/aws/d/aws_sqs_queue"

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
data "aws_sqs_queue" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_sqs_queue.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_sqs_queue.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_sqs_queue.this.tags
}

output "url" {
  description = "returns a string"
  value       = data.aws_sqs_queue.this.url
}

output "this" {
  value = aws_sqs_queue.this
}
```

[top](#index)