# aws_dynamodb_table

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
module "aws_dynamodb_table" {
  source = "./modules/aws/r/aws_dynamodb_table"

  # billing_mode - (optional) is a type of string
  billing_mode = null
  # hash_key - (required) is a type of string
  hash_key = null
  # name - (required) is a type of string
  name = null
  # range_key - (optional) is a type of string
  range_key = null
  # read_capacity - (optional) is a type of number
  read_capacity = null
  # stream_enabled - (optional) is a type of bool
  stream_enabled = null
  # stream_view_type - (optional) is a type of string
  stream_view_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # write_capacity - (optional) is a type of number
  write_capacity = null

  attribute = [{
    name = null
    type = null
  }]

  global_secondary_index = [{
    hash_key           = null
    name               = null
    non_key_attributes = []
    projection_type    = null
    range_key          = null
    read_capacity      = null
    write_capacity     = null
  }]

  local_secondary_index = [{
    name               = null
    non_key_attributes = []
    projection_type    = null
    range_key          = null
  }]

  point_in_time_recovery = [{
    enabled = null
  }]

  replica = [{
    region_name = null
  }]

  server_side_encryption = [{
    enabled     = null
    kms_key_arn = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  ttl = [{
    attribute_name = null
    enabled        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "billing_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hash_key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "range_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "read_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stream_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "stream_view_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "write_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "attribute" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
      type = string
    }
  ))
}

variable "global_secondary_index" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      hash_key           = string
      name               = string
      non_key_attributes = set(string)
      projection_type    = string
      range_key          = string
      read_capacity      = number
      write_capacity     = number
    }
  ))
  default = []
}

variable "local_secondary_index" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name               = string
      non_key_attributes = list(string)
      projection_type    = string
      range_key          = string
    }
  ))
  default = []
}

variable "point_in_time_recovery" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "replica" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      region_name = string
    }
  ))
  default = []
}

variable "server_side_encryption" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled     = bool
      kms_key_arn = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "ttl" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attribute_name = string
      enabled        = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dynamodb_table" "this" {
  # billing_mode - (optional) is a type of string
  billing_mode = var.billing_mode
  # hash_key - (required) is a type of string
  hash_key = var.hash_key
  # name - (required) is a type of string
  name = var.name
  # range_key - (optional) is a type of string
  range_key = var.range_key
  # read_capacity - (optional) is a type of number
  read_capacity = var.read_capacity
  # stream_enabled - (optional) is a type of bool
  stream_enabled = var.stream_enabled
  # stream_view_type - (optional) is a type of string
  stream_view_type = var.stream_view_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # write_capacity - (optional) is a type of number
  write_capacity = var.write_capacity

  dynamic "attribute" {
    for_each = var.attribute
    content {
      # name - (required) is a type of string
      name = attribute.value["name"]
      # type - (required) is a type of string
      type = attribute.value["type"]
    }
  }

  dynamic "global_secondary_index" {
    for_each = var.global_secondary_index
    content {
      # hash_key - (required) is a type of string
      hash_key = global_secondary_index.value["hash_key"]
      # name - (required) is a type of string
      name = global_secondary_index.value["name"]
      # non_key_attributes - (optional) is a type of set of string
      non_key_attributes = global_secondary_index.value["non_key_attributes"]
      # projection_type - (required) is a type of string
      projection_type = global_secondary_index.value["projection_type"]
      # range_key - (optional) is a type of string
      range_key = global_secondary_index.value["range_key"]
      # read_capacity - (optional) is a type of number
      read_capacity = global_secondary_index.value["read_capacity"]
      # write_capacity - (optional) is a type of number
      write_capacity = global_secondary_index.value["write_capacity"]
    }
  }

  dynamic "local_secondary_index" {
    for_each = var.local_secondary_index
    content {
      # name - (required) is a type of string
      name = local_secondary_index.value["name"]
      # non_key_attributes - (optional) is a type of list of string
      non_key_attributes = local_secondary_index.value["non_key_attributes"]
      # projection_type - (required) is a type of string
      projection_type = local_secondary_index.value["projection_type"]
      # range_key - (required) is a type of string
      range_key = local_secondary_index.value["range_key"]
    }
  }

  dynamic "point_in_time_recovery" {
    for_each = var.point_in_time_recovery
    content {
      # enabled - (required) is a type of bool
      enabled = point_in_time_recovery.value["enabled"]
    }
  }

  dynamic "replica" {
    for_each = var.replica
    content {
      # region_name - (required) is a type of string
      region_name = replica.value["region_name"]
    }
  }

  dynamic "server_side_encryption" {
    for_each = var.server_side_encryption
    content {
      # enabled - (required) is a type of bool
      enabled = server_side_encryption.value["enabled"]
      # kms_key_arn - (optional) is a type of string
      kms_key_arn = server_side_encryption.value["kms_key_arn"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "ttl" {
    for_each = var.ttl
    content {
      # attribute_name - (required) is a type of string
      attribute_name = ttl.value["attribute_name"]
      # enabled - (optional) is a type of bool
      enabled = ttl.value["enabled"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_dynamodb_table.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_dynamodb_table.this.id
}

output "stream_arn" {
  description = "returns a string"
  value       = aws_dynamodb_table.this.stream_arn
}

output "stream_label" {
  description = "returns a string"
  value       = aws_dynamodb_table.this.stream_label
}

output "stream_view_type" {
  description = "returns a string"
  value       = aws_dynamodb_table.this.stream_view_type
}

output "this" {
  value = aws_dynamodb_table.this
}
```

[top](#index)