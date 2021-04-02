# aws_s3_bucket_inventory

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
module "aws_s3_bucket_inventory" {
  source = "./modules/aws/r/aws_s3_bucket_inventory"

  # bucket - (required) is a type of string
  bucket = null
  # enabled - (optional) is a type of bool
  enabled = null
  # included_object_versions - (required) is a type of string
  included_object_versions = null
  # name - (required) is a type of string
  name = null
  # optional_fields - (optional) is a type of set of string
  optional_fields = []

  destination = [{
    bucket = [{
      account_id = null
      bucket_arn = null
      encryption = [{
        sse_kms = [{
          key_id = null
        }]
        sse_s3 = [{

        }]
      }]
      format = null
      prefix = null
    }]
  }]

  filter = [{
    prefix = null
  }]

  schedule = [{
    frequency = null
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

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "included_object_versions" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "optional_fields" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      bucket = list(object(
        {
          account_id = string
          bucket_arn = string
          encryption = list(object(
            {
              sse_kms = list(object(
                {
                  key_id = string
                }
              ))
              sse_s3 = list(object(
                {

                }
              ))
            }
          ))
          format = string
          prefix = string
        }
      ))
    }
  ))
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      prefix = string
    }
  ))
  default = []
}

variable "schedule" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      frequency = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_inventory" "this" {
  bucket                   = var.bucket
  enabled                  = var.enabled
  included_object_versions = var.included_object_versions
  name                     = var.name
  optional_fields          = var.optional_fields

  dynamic "destination" {
    for_each = var.destination
    content {

      dynamic "bucket" {
        for_each = destination.value.bucket
        content {
          account_id = bucket.value["account_id"]
          bucket_arn = bucket.value["bucket_arn"]
          format     = bucket.value["format"]
          prefix     = bucket.value["prefix"]

          dynamic "encryption" {
            for_each = bucket.value.encryption
            content {

              dynamic "sse_kms" {
                for_each = encryption.value.sse_kms
                content {
                  key_id = sse_kms.value["key_id"]
                }
              }

              dynamic "sse_s3" {
                for_each = encryption.value.sse_s3
                content {
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      prefix = filter.value["prefix"]
    }
  }

  dynamic "schedule" {
    for_each = var.schedule
    content {
      frequency = schedule.value["frequency"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_inventory.this.id
}

output "this" {
  value = aws_s3_bucket_inventory.this
}
```

[top](#index)