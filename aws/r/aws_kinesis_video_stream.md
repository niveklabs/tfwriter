# aws_kinesis_video_stream

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
module "aws_kinesis_video_stream" {
  source = "./modules/aws/r/aws_kinesis_video_stream"

  # data_retention_in_hours - (optional) is a type of number
  data_retention_in_hours = null
  # device_name - (optional) is a type of string
  device_name = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # media_type - (optional) is a type of string
  media_type = null
  # name - (required) is a type of string
  name = null
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
variable "data_retention_in_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "media_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "aws_kinesis_video_stream" "this" {
  data_retention_in_hours = var.data_retention_in_hours
  device_name             = var.device_name
  kms_key_id              = var.kms_key_id
  media_type              = var.media_type
  name                    = var.name
  tags                    = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = aws_kinesis_video_stream.this.arn
}

output "creation_time" {
  description = "returns a string"
  value       = aws_kinesis_video_stream.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = aws_kinesis_video_stream.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_kinesis_video_stream.this.kms_key_id
}

output "version" {
  description = "returns a string"
  value       = aws_kinesis_video_stream.this.version
}

output "this" {
  value = aws_kinesis_video_stream.this
}
```

[top](#index)