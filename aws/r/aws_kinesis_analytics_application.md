# aws_kinesis_analytics_application

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
module "aws_kinesis_analytics_application" {
  source = "./modules/aws/r/aws_kinesis_analytics_application"

  # code - (optional) is a type of string
  code = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # start_application - (optional) is a type of bool
  start_application = null
  # tags - (optional) is a type of map of string
  tags = {}

  cloudwatch_logging_options = [{
    id             = null
    log_stream_arn = null
    role_arn       = null
  }]

  inputs = [{
    id = null
    kinesis_firehose = [{
      resource_arn = null
      role_arn     = null
    }]
    kinesis_stream = [{
      resource_arn = null
      role_arn     = null
    }]
    name_prefix = null
    parallelism = [{
      count = null
    }]
    processing_configuration = [{
      lambda = [{
        resource_arn = null
        role_arn     = null
      }]
    }]
    schema = [{
      record_columns = [{
        mapping  = null
        name     = null
        sql_type = null
      }]
      record_encoding = null
      record_format = [{
        mapping_parameters = [{
          csv = [{
            record_column_delimiter = null
            record_row_delimiter    = null
          }]
          json = [{
            record_row_path = null
          }]
        }]
        record_format_type = null
      }]
    }]
    starting_position_configuration = [{
      starting_position = null
    }]
    stream_names = []
  }]

  outputs = [{
    id = null
    kinesis_firehose = [{
      resource_arn = null
      role_arn     = null
    }]
    kinesis_stream = [{
      resource_arn = null
      role_arn     = null
    }]
    lambda = [{
      resource_arn = null
      role_arn     = null
    }]
    name = null
    schema = [{
      record_format_type = null
    }]
  }]

  reference_data_sources = [{
    id = null
    s3 = [{
      bucket_arn = null
      file_key   = null
      role_arn   = null
    }]
    schema = [{
      record_columns = [{
        mapping  = null
        name     = null
        sql_type = null
      }]
      record_encoding = null
      record_format = [{
        mapping_parameters = [{
          csv = [{
            record_column_delimiter = null
            record_row_delimiter    = null
          }]
          json = [{
            record_row_path = null
          }]
        }]
        record_format_type = null
      }]
    }]
    table_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "start_application" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cloudwatch_logging_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id             = string
      log_stream_arn = string
      role_arn       = string
    }
  ))
  default = []
}

variable "inputs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id = string
      kinesis_firehose = list(object(
        {
          resource_arn = string
          role_arn     = string
        }
      ))
      kinesis_stream = list(object(
        {
          resource_arn = string
          role_arn     = string
        }
      ))
      name_prefix = string
      parallelism = list(object(
        {
          count = number
        }
      ))
      processing_configuration = list(object(
        {
          lambda = list(object(
            {
              resource_arn = string
              role_arn     = string
            }
          ))
        }
      ))
      schema = list(object(
        {
          record_columns = list(object(
            {
              mapping  = string
              name     = string
              sql_type = string
            }
          ))
          record_encoding = string
          record_format = list(object(
            {
              mapping_parameters = list(object(
                {
                  csv = list(object(
                    {
                      record_column_delimiter = string
                      record_row_delimiter    = string
                    }
                  ))
                  json = list(object(
                    {
                      record_row_path = string
                    }
                  ))
                }
              ))
              record_format_type = string
            }
          ))
        }
      ))
      starting_position_configuration = list(object(
        {
          starting_position = string
        }
      ))
      stream_names = list(string)
    }
  ))
  default = []
}

variable "outputs" {
  description = "nested block: NestingSet, min items: 0, max items: 3"
  type = set(object(
    {
      id = string
      kinesis_firehose = list(object(
        {
          resource_arn = string
          role_arn     = string
        }
      ))
      kinesis_stream = list(object(
        {
          resource_arn = string
          role_arn     = string
        }
      ))
      lambda = list(object(
        {
          resource_arn = string
          role_arn     = string
        }
      ))
      name = string
      schema = list(object(
        {
          record_format_type = string
        }
      ))
    }
  ))
  default = []
}

variable "reference_data_sources" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id = string
      s3 = list(object(
        {
          bucket_arn = string
          file_key   = string
          role_arn   = string
        }
      ))
      schema = list(object(
        {
          record_columns = list(object(
            {
              mapping  = string
              name     = string
              sql_type = string
            }
          ))
          record_encoding = string
          record_format = list(object(
            {
              mapping_parameters = list(object(
                {
                  csv = list(object(
                    {
                      record_column_delimiter = string
                      record_row_delimiter    = string
                    }
                  ))
                  json = list(object(
                    {
                      record_row_path = string
                    }
                  ))
                }
              ))
              record_format_type = string
            }
          ))
        }
      ))
      table_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_kinesis_analytics_application" "this" {
  code              = var.code
  description       = var.description
  name              = var.name
  start_application = var.start_application
  tags              = var.tags

  dynamic "cloudwatch_logging_options" {
    for_each = var.cloudwatch_logging_options
    content {
      log_stream_arn = cloudwatch_logging_options.value["log_stream_arn"]
      role_arn       = cloudwatch_logging_options.value["role_arn"]
    }
  }

  dynamic "inputs" {
    for_each = var.inputs
    content {
      name_prefix = inputs.value["name_prefix"]

      dynamic "kinesis_firehose" {
        for_each = inputs.value.kinesis_firehose
        content {
          resource_arn = kinesis_firehose.value["resource_arn"]
          role_arn     = kinesis_firehose.value["role_arn"]
        }
      }

      dynamic "kinesis_stream" {
        for_each = inputs.value.kinesis_stream
        content {
          resource_arn = kinesis_stream.value["resource_arn"]
          role_arn     = kinesis_stream.value["role_arn"]
        }
      }

      dynamic "parallelism" {
        for_each = inputs.value.parallelism
        content {
          count = parallelism.value["count"]
        }
      }

      dynamic "processing_configuration" {
        for_each = inputs.value.processing_configuration
        content {

          dynamic "lambda" {
            for_each = processing_configuration.value.lambda
            content {
              resource_arn = lambda.value["resource_arn"]
              role_arn     = lambda.value["role_arn"]
            }
          }

        }
      }

      dynamic "schema" {
        for_each = inputs.value.schema
        content {
          record_encoding = schema.value["record_encoding"]

          dynamic "record_columns" {
            for_each = schema.value.record_columns
            content {
              mapping  = record_columns.value["mapping"]
              name     = record_columns.value["name"]
              sql_type = record_columns.value["sql_type"]
            }
          }

          dynamic "record_format" {
            for_each = schema.value.record_format
            content {

              dynamic "mapping_parameters" {
                for_each = record_format.value.mapping_parameters
                content {

                  dynamic "csv" {
                    for_each = mapping_parameters.value.csv
                    content {
                      record_column_delimiter = csv.value["record_column_delimiter"]
                      record_row_delimiter    = csv.value["record_row_delimiter"]
                    }
                  }

                  dynamic "json" {
                    for_each = mapping_parameters.value.json
                    content {
                      record_row_path = json.value["record_row_path"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "starting_position_configuration" {
        for_each = inputs.value.starting_position_configuration
        content {
          starting_position = starting_position_configuration.value["starting_position"]
        }
      }

    }
  }

  dynamic "outputs" {
    for_each = var.outputs
    content {
      name = outputs.value["name"]

      dynamic "kinesis_firehose" {
        for_each = outputs.value.kinesis_firehose
        content {
          resource_arn = kinesis_firehose.value["resource_arn"]
          role_arn     = kinesis_firehose.value["role_arn"]
        }
      }

      dynamic "kinesis_stream" {
        for_each = outputs.value.kinesis_stream
        content {
          resource_arn = kinesis_stream.value["resource_arn"]
          role_arn     = kinesis_stream.value["role_arn"]
        }
      }

      dynamic "lambda" {
        for_each = outputs.value.lambda
        content {
          resource_arn = lambda.value["resource_arn"]
          role_arn     = lambda.value["role_arn"]
        }
      }

      dynamic "schema" {
        for_each = outputs.value.schema
        content {
          record_format_type = schema.value["record_format_type"]
        }
      }

    }
  }

  dynamic "reference_data_sources" {
    for_each = var.reference_data_sources
    content {
      table_name = reference_data_sources.value["table_name"]

      dynamic "s3" {
        for_each = reference_data_sources.value.s3
        content {
          bucket_arn = s3.value["bucket_arn"]
          file_key   = s3.value["file_key"]
          role_arn   = s3.value["role_arn"]
        }
      }

      dynamic "schema" {
        for_each = reference_data_sources.value.schema
        content {
          record_encoding = schema.value["record_encoding"]

          dynamic "record_columns" {
            for_each = schema.value.record_columns
            content {
              mapping  = record_columns.value["mapping"]
              name     = record_columns.value["name"]
              sql_type = record_columns.value["sql_type"]
            }
          }

          dynamic "record_format" {
            for_each = schema.value.record_format
            content {

              dynamic "mapping_parameters" {
                for_each = record_format.value.mapping_parameters
                content {

                  dynamic "csv" {
                    for_each = mapping_parameters.value.csv
                    content {
                      record_column_delimiter = csv.value["record_column_delimiter"]
                      record_row_delimiter    = csv.value["record_row_delimiter"]
                    }
                  }

                  dynamic "json" {
                    for_each = mapping_parameters.value.json
                    content {
                      record_row_path = json.value["record_row_path"]
                    }
                  }

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
output "arn" {
  description = "returns a string"
  value       = aws_kinesis_analytics_application.this.arn
}

output "create_timestamp" {
  description = "returns a string"
  value       = aws_kinesis_analytics_application.this.create_timestamp
}

output "id" {
  description = "returns a string"
  value       = aws_kinesis_analytics_application.this.id
}

output "last_update_timestamp" {
  description = "returns a string"
  value       = aws_kinesis_analytics_application.this.last_update_timestamp
}

output "status" {
  description = "returns a string"
  value       = aws_kinesis_analytics_application.this.status
}

output "version" {
  description = "returns a number"
  value       = aws_kinesis_analytics_application.this.version
}

output "this" {
  value = aws_kinesis_analytics_application.this
}
```

[top](#index)