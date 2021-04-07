# aws_wafv2_web_acl_logging_configuration

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
module "aws_wafv2_web_acl_logging_configuration" {
  source = "./modules/aws/r/aws_wafv2_web_acl_logging_configuration"

  # log_destination_configs - (required) is a type of set of string
  log_destination_configs = []
  # resource_arn - (required) is a type of string
  resource_arn = null

  redacted_fields = [{
    all_query_arguments = [{

    }]
    body = [{

    }]
    method = [{

    }]
    query_string = [{

    }]
    single_header = [{
      name = null
    }]
    single_query_argument = [{
      name = null
    }]
    uri_path = [{

    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "log_destination_configs" {
  description = "(required) - AWS Kinesis Firehose Delivery Stream ARNs"
  type        = set(string)
}

variable "resource_arn" {
  description = "(required) - AWS WebACL ARN"
  type        = string
}

variable "redacted_fields" {
  description = "nested block: NestingList, min items: 0, max items: 100"
  type = set(object(
    {
      all_query_arguments = list(object(
        {

        }
      ))
      body = list(object(
        {

        }
      ))
      method = list(object(
        {

        }
      ))
      query_string = list(object(
        {

        }
      ))
      single_header = list(object(
        {
          name = string
        }
      ))
      single_query_argument = list(object(
        {
          name = string
        }
      ))
      uri_path = list(object(
        {

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
resource "aws_wafv2_web_acl_logging_configuration" "this" {
  # log_destination_configs - (required) is a type of set of string
  log_destination_configs = var.log_destination_configs
  # resource_arn - (required) is a type of string
  resource_arn = var.resource_arn

  dynamic "redacted_fields" {
    for_each = var.redacted_fields
    content {

      dynamic "all_query_arguments" {
        for_each = redacted_fields.value.all_query_arguments
        content {
        }
      }

      dynamic "body" {
        for_each = redacted_fields.value.body
        content {
        }
      }

      dynamic "method" {
        for_each = redacted_fields.value.method
        content {
        }
      }

      dynamic "query_string" {
        for_each = redacted_fields.value.query_string
        content {
        }
      }

      dynamic "single_header" {
        for_each = redacted_fields.value.single_header
        content {
          # name - (required) is a type of string
          name = single_header.value["name"]
        }
      }

      dynamic "single_query_argument" {
        for_each = redacted_fields.value.single_query_argument
        content {
          # name - (required) is a type of string
          name = single_query_argument.value["name"]
        }
      }

      dynamic "uri_path" {
        for_each = redacted_fields.value.uri_path
        content {
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
  value       = aws_wafv2_web_acl_logging_configuration.this.id
}

output "this" {
  value = aws_wafv2_web_acl_logging_configuration.this
}
```

[top](#index)