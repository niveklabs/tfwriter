# aws_cloudfront_realtime_log_config

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_cloudfront_realtime_log_config" {
  source = "./modules/aws/r/aws_cloudfront_realtime_log_config"

  # fields - (required) is a type of set of string
  fields = []
  # name - (required) is a type of string
  name = null
  # sampling_rate - (required) is a type of number
  sampling_rate = null

  endpoint = [{
    kinesis_stream_config = [{
      role_arn   = null
      stream_arn = null
    }]
    stream_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "fields" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sampling_rate" {
  description = "(required)"
  type        = number
}

variable "endpoint" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      kinesis_stream_config = list(object(
        {
          role_arn   = string
          stream_arn = string
        }
      ))
      stream_type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudfront_realtime_log_config" "this" {
  fields        = var.fields
  name          = var.name
  sampling_rate = var.sampling_rate

  dynamic "endpoint" {
    for_each = var.endpoint
    content {
      stream_type = endpoint.value["stream_type"]

      dynamic "kinesis_stream_config" {
        for_each = endpoint.value.kinesis_stream_config
        content {
          role_arn   = kinesis_stream_config.value["role_arn"]
          stream_arn = kinesis_stream_config.value["stream_arn"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudfront_realtime_log_config.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudfront_realtime_log_config.this.id
}

output "this" {
  value = aws_cloudfront_realtime_log_config.this
}
```

[top](#index)