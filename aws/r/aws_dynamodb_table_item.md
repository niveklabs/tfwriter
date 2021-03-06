# aws_dynamodb_table_item

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
module "aws_dynamodb_table_item" {
  source = "./modules/aws/r/aws_dynamodb_table_item"

  # hash_key - (required) is a type of string
  hash_key = null
  # item - (required) is a type of string
  item = null
  # range_key - (optional) is a type of string
  range_key = null
  # table_name - (required) is a type of string
  table_name = null
}
```

[top](#index)

### Variables

```terraform
variable "hash_key" {
  description = "(required)"
  type        = string
}

variable "item" {
  description = "(required)"
  type        = string
}

variable "range_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_dynamodb_table_item" "this" {
  # hash_key - (required) is a type of string
  hash_key = var.hash_key
  # item - (required) is a type of string
  item = var.item
  # range_key - (optional) is a type of string
  range_key = var.range_key
  # table_name - (required) is a type of string
  table_name = var.table_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_dynamodb_table_item.this.id
}

output "this" {
  value = aws_dynamodb_table_item.this
}
```

[top](#index)