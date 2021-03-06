# aws_s3_bucket_analytics_configuration

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
module "aws_s3_bucket_analytics_configuration" {
  source = "./modules/aws/r/aws_s3_bucket_analytics_configuration"

  # bucket - (required) is a type of string
  bucket = null
  # name - (required) is a type of string
  name = null

  filter = [{
    prefix = null
    tags   = {}
  }]

  storage_class_analysis = [{
    data_export = [{
      destination = [{
        s3_bucket_destination = [{
          bucket_account_id = null
          bucket_arn        = null
          format            = null
          prefix            = null
        }]
      }]
      output_schema_version = null
    }]
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      prefix = string
      tags   = map(string)
    }
  ))
  default = []
}

variable "storage_class_analysis" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_export = list(object(
        {
          destination = list(object(
            {
              s3_bucket_destination = list(object(
                {
                  bucket_account_id = string
                  bucket_arn        = string
                  format            = string
                  prefix            = string
                }
              ))
            }
          ))
          output_schema_version = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_analytics_configuration" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # name - (required) is a type of string
  name = var.name

  dynamic "filter" {
    for_each = var.filter
    content {
      # prefix - (optional) is a type of string
      prefix = filter.value["prefix"]
      # tags - (optional) is a type of map of string
      tags = filter.value["tags"]
    }
  }

  dynamic "storage_class_analysis" {
    for_each = var.storage_class_analysis
    content {

      dynamic "data_export" {
        for_each = storage_class_analysis.value.data_export
        content {
          # output_schema_version - (optional) is a type of string
          output_schema_version = data_export.value["output_schema_version"]

          dynamic "destination" {
            for_each = data_export.value.destination
            content {

              dynamic "s3_bucket_destination" {
                for_each = destination.value.s3_bucket_destination
                content {
                  # bucket_account_id - (optional) is a type of string
                  bucket_account_id = s3_bucket_destination.value["bucket_account_id"]
                  # bucket_arn - (required) is a type of string
                  bucket_arn = s3_bucket_destination.value["bucket_arn"]
                  # format - (optional) is a type of string
                  format = s3_bucket_destination.value["format"]
                  # prefix - (optional) is a type of string
                  prefix = s3_bucket_destination.value["prefix"]
                }
              }

            }
          }

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
  value       = aws_s3_bucket_analytics_configuration.this.id
}

output "this" {
  value = aws_s3_bucket_analytics_configuration.this
}
```

[top](#index)