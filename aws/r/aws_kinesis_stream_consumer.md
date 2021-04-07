# aws_kinesis_stream_consumer

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
module "aws_kinesis_stream_consumer" {
  source = "./modules/aws/r/aws_kinesis_stream_consumer"

  # name - (required) is a type of string
  name = null
  # stream_arn - (required) is a type of string
  stream_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "stream_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_kinesis_stream_consumer" "this" {
  # name - (required) is a type of string
  name = var.name
  # stream_arn - (required) is a type of string
  stream_arn = var.stream_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_kinesis_stream_consumer.this.arn
}

output "creation_timestamp" {
  description = "returns a string"
  value       = aws_kinesis_stream_consumer.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = aws_kinesis_stream_consumer.this.id
}

output "this" {
  value = aws_kinesis_stream_consumer.this
}
```

[top](#index)