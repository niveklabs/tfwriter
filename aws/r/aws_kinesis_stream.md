# aws_kinesis_stream

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
module "aws_kinesis_stream" {
  source = "./modules/aws/r/aws_kinesis_stream"

  # arn - (optional) is a type of string
  arn = null
  # encryption_type - (optional) is a type of string
  encryption_type = null
  # enforce_consumer_deletion - (optional) is a type of bool
  enforce_consumer_deletion = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (required) is a type of string
  name = null
  # retention_period - (optional) is a type of number
  retention_period = null
  # shard_count - (required) is a type of number
  shard_count = null
  # shard_level_metrics - (optional) is a type of set of string
  shard_level_metrics = []
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
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

variable "encryption_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enforce_consumer_deletion" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shard_count" {
  description = "(required)"
  type        = number
}

variable "shard_level_metrics" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
```

[top](#index)

### Resource

```terraform
resource "aws_kinesis_stream" "this" {
  # arn - (optional) is a type of string
  arn = var.arn
  # encryption_type - (optional) is a type of string
  encryption_type = var.encryption_type
  # enforce_consumer_deletion - (optional) is a type of bool
  enforce_consumer_deletion = var.enforce_consumer_deletion
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # name - (required) is a type of string
  name = var.name
  # retention_period - (optional) is a type of number
  retention_period = var.retention_period
  # shard_count - (required) is a type of number
  shard_count = var.shard_count
  # shard_level_metrics - (optional) is a type of set of string
  shard_level_metrics = var.shard_level_metrics
  # tags - (optional) is a type of map of string
  tags = var.tags

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

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_kinesis_stream.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_kinesis_stream.this.id
}

output "this" {
  value = aws_kinesis_stream.this
}
```

[top](#index)