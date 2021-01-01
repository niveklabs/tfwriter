# aws_kinesis_stream

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
module "aws_kinesis_stream" {
  source = "./modules/aws/d/aws_kinesis_stream"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
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

```hcl
data "aws_kinesis_stream" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_kinesis_stream.this.arn
}

output "closed_shards" {
  description = "returns a set of string"
  value       = data.aws_kinesis_stream.this.closed_shards
}

output "creation_timestamp" {
  description = "returns a number"
  value       = data.aws_kinesis_stream.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = data.aws_kinesis_stream.this.id
}

output "open_shards" {
  description = "returns a set of string"
  value       = data.aws_kinesis_stream.this.open_shards
}

output "retention_period" {
  description = "returns a number"
  value       = data.aws_kinesis_stream.this.retention_period
}

output "shard_level_metrics" {
  description = "returns a set of string"
  value       = data.aws_kinesis_stream.this.shard_level_metrics
}

output "status" {
  description = "returns a string"
  value       = data.aws_kinesis_stream.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_kinesis_stream.this.tags
}

output "this" {
  value = aws_kinesis_stream.this
}
```

[top](#index)