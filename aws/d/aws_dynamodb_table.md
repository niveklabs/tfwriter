# aws_dynamodb_table

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
module "aws_dynamodb_table" {
  source = "./modules/aws/d/aws_dynamodb_table"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  server_side_encryption = [{
    enabled     = null
    kms_key_arn = null
  }]
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

variable "server_side_encryption" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled     = bool
      kms_key_arn = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_dynamodb_table" "this" {
  name = var.name
  tags = var.tags

  dynamic "server_side_encryption" {
    for_each = var.server_side_encryption
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.arn
}

output "attribute" {
  description = "returns a set of object"
  value       = data.aws_dynamodb_table.this.attribute
}

output "billing_mode" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.billing_mode
}

output "global_secondary_index" {
  description = "returns a set of object"
  value       = data.aws_dynamodb_table.this.global_secondary_index
}

output "hash_key" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.hash_key
}

output "id" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.id
}

output "local_secondary_index" {
  description = "returns a set of object"
  value       = data.aws_dynamodb_table.this.local_secondary_index
}

output "point_in_time_recovery" {
  description = "returns a list of object"
  value       = data.aws_dynamodb_table.this.point_in_time_recovery
}

output "range_key" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.range_key
}

output "read_capacity" {
  description = "returns a number"
  value       = data.aws_dynamodb_table.this.read_capacity
}

output "replica" {
  description = "returns a set of object"
  value       = data.aws_dynamodb_table.this.replica
}

output "stream_arn" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.stream_arn
}

output "stream_enabled" {
  description = "returns a bool"
  value       = data.aws_dynamodb_table.this.stream_enabled
}

output "stream_label" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.stream_label
}

output "stream_view_type" {
  description = "returns a string"
  value       = data.aws_dynamodb_table.this.stream_view_type
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_dynamodb_table.this.tags
}

output "ttl" {
  description = "returns a set of object"
  value       = data.aws_dynamodb_table.this.ttl
}

output "write_capacity" {
  description = "returns a number"
  value       = data.aws_dynamodb_table.this.write_capacity
}

output "this" {
  value = aws_dynamodb_table.this
}
```

[top](#index)