# aws_sqs_queue_policy

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
module "aws_sqs_queue_policy" {
  source = "./modules/aws/r/aws_sqs_queue_policy"

  # policy - (required) is a type of string
  policy = null
  # queue_url - (required) is a type of string
  queue_url = null
}
```

[top](#index)

### Variables

```terraform
variable "policy" {
  description = "(required)"
  type        = string
}

variable "queue_url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_sqs_queue_policy" "this" {
  policy    = var.policy
  queue_url = var.queue_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_sqs_queue_policy.this.id
}

output "this" {
  value = aws_sqs_queue_policy.this
}
```

[top](#index)