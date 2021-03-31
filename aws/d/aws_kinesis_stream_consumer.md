# aws_kinesis_stream_consumer

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
module "aws_kinesis_stream_consumer" {
  source = "./modules/aws/d/aws_kinesis_stream_consumer"

  # arn - (optional) is a type of string
  arn = null
  # name - (optional) is a type of string
  name = null
  # stream_arn - (required) is a type of string
  stream_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stream_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_kinesis_stream_consumer" "this" {
  arn        = var.arn
  name       = var.name
  stream_arn = var.stream_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_kinesis_stream_consumer.this.arn
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.aws_kinesis_stream_consumer.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = data.aws_kinesis_stream_consumer.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_kinesis_stream_consumer.this.name
}

output "status" {
  description = "returns a string"
  value       = data.aws_kinesis_stream_consumer.this.status
}

output "this" {
  value = aws_kinesis_stream_consumer.this
}
```

[top](#index)