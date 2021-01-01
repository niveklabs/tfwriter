# aws_s3control_bucket_lifecycle_configuration

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

```hcl
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
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

```hcl
resource "aws_s3control_bucket_lifecycle_configuration" "this" {
  bucket = var.bucket

  dynamic "rule" {
    for_each = var.rule
    content {
      id     = rule.value["id"]
      status = rule.value["status"]

      dynamic "abort_incomplete_multipart_upload" {
        for_each = rule.value.abort_incomplete_multipart_upload
        content {
          days_after_initiation = abort_incomplete_multipart_upload.value["days_after_initiation"]
        }
      }

      dynamic "expiration" {
        for_each = rule.value.expiration
        content {
          date                         = expiration.value["date"]
          days                         = expiration.value["days"]
          expired_object_delete_marker = expiration.value["expired_object_delete_marker"]
        }
      }

      dynamic "filter" {
        for_each = rule.value.filter
        content {
          prefix = filter.value["prefix"]
          tags   = filter.value["tags"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_s3control_bucket_lifecycle_configuration.this.id
}

output "this" {
  value = aws_s3control_bucket_lifecycle_configuration.this
}
```

[top](#index)