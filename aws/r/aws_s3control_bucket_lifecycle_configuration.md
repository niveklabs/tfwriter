# aws_s3control_bucket_lifecycle_configuration

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
module "aws_s3control_bucket_lifecycle_configuration" {
  source = "./modules/aws/r/aws_s3control_bucket_lifecycle_configuration"

  # bucket - (required) is a type of string
  bucket = null

  rule = [{
    abort_incomplete_multipart_upload = [{
      days_after_initiation = null
    }]
    expiration = [{
      date                         = null
      days                         = null
      expired_object_delete_marker = null
    }]
    filter = [{
      prefix = null
      tags   = {}
    }]
    id     = null
    status = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      abort_incomplete_multipart_upload = list(object(
        {
          days_after_initiation = number
        }
      ))
      expiration = list(object(
        {
          date                         = string
          days                         = number
          expired_object_delete_marker = bool
        }
      ))
      filter = list(object(
        {
          prefix = string
          tags   = map(string)
        }
      ))
      id     = string
      status = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3control_bucket_lifecycle_configuration" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket

  dynamic "rule" {
    for_each = var.rule
    content {
      # id - (required) is a type of string
      id = rule.value["id"]
      # status - (optional) is a type of string
      status = rule.value["status"]

      dynamic "abort_incomplete_multipart_upload" {
        for_each = rule.value.abort_incomplete_multipart_upload
        content {
          # days_after_initiation - (required) is a type of number
          days_after_initiation = abort_incomplete_multipart_upload.value["days_after_initiation"]
        }
      }

      dynamic "expiration" {
        for_each = rule.value.expiration
        content {
          # date - (optional) is a type of string
          date = expiration.value["date"]
          # days - (optional) is a type of number
          days = expiration.value["days"]
          # expired_object_delete_marker - (optional) is a type of bool
          expired_object_delete_marker = expiration.value["expired_object_delete_marker"]
        }
      }

      dynamic "filter" {
        for_each = rule.value.filter
        content {
          # prefix - (optional) is a type of string
          prefix = filter.value["prefix"]
          # tags - (optional) is a type of map of string
          tags = filter.value["tags"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_s3control_bucket_lifecycle_configuration.this.id
}

output "this" {
  value = aws_s3control_bucket_lifecycle_configuration.this
}
```

[top](#index)