# aws_kinesisanalyticsv2_application

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_kinesisanalyticsv2_application" {
  source = "./modules/aws/r/aws_kinesisanalyticsv2_application"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # runtime_environment - (required) is a type of string
  runtime_environment = null
  # service_execution_role - (required) is a type of string
  service_execution_role = null
  # tags - (optional) is a type of map of string
  tags = {}

  application_configuration = [{
    application_code_configuration = [{
      code_content = [{
        s3_content_location = [{
          bucket_arn     = null
          file_key       = null
          object_version = null
        }]
        text_content = null
      }]
      code_content_type = null
    }]
    application_snapshot_configuration = [{
      snapshots_enabled = null
    }]
    environment_properties = [{
      property_group = [{
        property_group_id = null
        property_map      = {}
      }]
    }]
    flink_application_configuration = [{
      checkpoint_configuration = [{
        checkpoint_interval           = null
        checkpointing_enabled         = null
        configuration_type            = null
        min_pause_between_checkpoints = null
      }]
      monitoring_configuration = [{
        configuration_type = null
        log_level          = null
        metrics_level      = null
      }]
      parallelism_configuration = [{
        auto_scaling_enabled = null
        configuration_type   = null
        parallelism          = null
        parallelism_per_kpu  = null
      }]
    }]
    sql_application_configuration = [{
      input = [{
        in_app_stream_names = []
        input_id            = null
        input_parallelism = [{
          count = null
        }]
        input_processing_configuration = [{
          input_lambda_processor = [{
            resource_arn = null
          }]
        }]
        input_schema = [{
          record_column = [{
            mapping  = null
            name     = null
            sql_type = null
          }]
          record_encoding = null
          record_format = [{
            mapping_parameters = [{
              csv_mapping_parameters = [{
                record_column_delimiter = null
                record_row_delimiter    = null
              }]
              json_mapping_parameters = [{
                record_row_path = null
              }]
            }]
            record_format_type = null
          }]
        }]
        input_starting_position_configuration = [{
          input_starting_position = null
        }]
        kinesis_firehose_input = [{
          resource_arn = null
        }]
        kinesis_streams_input = [{
          resource_arn = null
        }]
        name_prefix = null
      }]
      output = [{
        destination_schema = [{
          record_format_type = null
        }]
        kinesis_firehose_output = [{
          resource_arn = null
        }]
        kinesis_streams_output = [{
          resource_arn = null
        }]
        lambda_output = [{
          resource_arn = null
        }]
        name      = null
        output_id = null
      }]
      reference_data_source = [{
        reference_id = null
        reference_schema = [{
          record_column = [{
            mapping  = null
            name     = null
            sql_type = null
          }]
          record_encoding = null
          record_format = [{
            mapping_parameters = [{
              csv_mapping_parameters = [{
                record_column_delimiter = null
                record_row_delimiter    = null
              }]
              json_mapping_parameters = [{
                record_row_path = null
              }]
            }]
            record_format_type = null
          }]
        }]
        s3_reference_data_source = [{
          bucket_arn = null
          file_key   = null
        }]
        table_name = null
      }]
    }]
    vpc_configuration = [{
      security_group_ids   = []
      subnet_ids           = []
      vpc_configuration_id = null
      vpc_id               = null
    }]
  }]

  cloudwatch_logging_options = [{
    cloudwatch_logging_option_id = null
    log_stream_arn               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "runtime_environment" {
  description = "(required)"
  type        = string
}

variable "service_execution_role" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "application_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      application_code_configuration = list(object(
        {
          code_content = list(object(
            {
              s3_content_location = list(object(
                {
                  bucket_arn     = string
                  file_key       = string
                  object_version = string
                }
              ))
              text_content = string
            }
          ))
          code_content_type = string
        }
      ))
      application_snapshot_configuration = list(object(
        {
          snapshots_enabled = bool
        }
      ))
      environment_properties = list(object(
        {
          property_group = set(object(
            {
              property_group_id = string
              property_map      = map(string)
            }
          ))
        }
      ))
      flink_application_configuration = list(object(
        {
          checkpoint_configuration = list(object(
            {
              checkpoint_interval           = number
              checkpointing_enabled         = bool
              configuration_type            = string
              min_pause_between_checkpoints = number
            }
          ))
          monitoring_configuration = list(object(
            {
              configuration_type = string
              log_level          = string
              metrics_level      = string
            }
          ))
          parallelism_configuration = list(object(
            {
              auto_scaling_enabled = bool
              configuration_type   = string
              parallelism          = number
              parallelism_per_kpu  = number
            }
          ))
        }
      ))
      sql_application_configuration = list(object(
        {
          input = list(object(
            {
              in_app_stream_names = list(string)
              input_id            = string
              input_parallelism = list(object(
                {
                  count = number
                }
              ))
              input_processing_configuration = list(object(
                {
                  input_lambda_processor = list(object(
                    {
                      resource_arn = string
                    }
                  ))
                }
              ))
              input_schema = list(object(
                {
                  record_column = list(object(
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
                          csv_mapping_parameters = list(object(
                            {
                              record_column_delimiter = string
                              record_row_delimiter    = string
                            }
                          ))
                          json_mapping_parameters = list(object(
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
              input_starting_position_configuration = list(object(
                {
                  input_starting_position = string
                }
              ))
              kinesis_firehose_input = list(object(
                {
                  resource_arn = string
                }
              ))
              kinesis_streams_input = list(object(
                {
                  resource_arn = string
                }
              ))
              name_prefix = string
            }
          ))
          output = set(object(
            {
              destination_schema = list(object(
                {
                  record_format_type = string
                }
              ))
              kinesis_firehose_output = list(object(
                {
                  resource_arn = string
                }
              ))
              kinesis_streams_output = list(object(
                {
                  resource_arn = string
                }
              ))
              lambda_output = list(object(
                {
                  resource_arn = string
                }
              ))
              name      = string
              output_id = string
            }
          ))
          reference_data_source = list(object(
            {
              reference_id = string
              reference_schema = list(object(
                {
                  record_column = list(object(
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
                          csv_mapping_parameters = list(object(
                            {
                              record_column_delimiter = string
                              record_row_delimiter    = string
                            }
                          ))
                          json_mapping_parameters = list(object(
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
              s3_reference_data_source = list(object(
                {
                  bucket_arn = string
                  file_key   = string
                }
              ))
              table_name = string
            }
          ))
        }
      ))
      vpc_configuration = list(object(
        {
          security_group_ids   = set(string)
          subnet_ids           = set(string)
          vpc_configuration_id = string
          vpc_id               = string
        }
      ))
    }
  ))
  default = []
}

variable "cloudwatch_logging_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudwatch_logging_option_id = string
      log_stream_arn               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_kinesisanalyticsv2_application" "this" {
  description            = var.description
  name                   = var.name
  runtime_environment    = var.runtime_environment
  service_execution_role = var.service_execution_role
  tags                   = var.tags

  dynamic "application_configuration" {
    for_each = var.application_configuration
    content {

      dynamic "application_code_configuration" {
        for_each = application_configuration.value.application_code_configuration
        content {
          code_content_type = application_code_configuration.value["code_content_type"]

          dynamic "code_content" {
            for_each = application_code_configuration.value.code_content
            content {
              text_content = code_content.value["text_content"]

              dynamic "s3_content_location" {
                for_each = code_content.value.s3_content_location
                content {
                  bucket_arn     = s3_content_location.value["bucket_arn"]
                  file_key       = s3_content_location.value["file_key"]
                  object_version = s3_content_location.value["object_version"]
                }
              }

            }
          }

        }
      }

      dynamic "application_snapshot_configuration" {
        for_each = application_configuration.value.application_snapshot_configuration
        content {
          snapshots_enabled = application_snapshot_configuration.value["snapshots_enabled"]
        }
      }

      dynamic "environment_properties" {
        for_each = application_configuration.value.environment_properties
        content {

          dynamic "property_group" {
            for_each = environment_properties.value.property_group
            content {
              property_group_id = property_group.value["property_group_id"]
              property_map      = property_group.value["property_map"]
            }
          }

        }
      }

      dynamic "flink_application_configuration" {
        for_each = application_configuration.value.flink_application_configuration
        content {

          dynamic "checkpoint_configuration" {
            for_each = flink_application_configuration.value.checkpoint_configuration
            content {
              checkpoint_interval           = checkpoint_configuration.value["checkpoint_interval"]
              checkpointing_enabled         = checkpoint_configuration.value["checkpointing_enabled"]
              configuration_type            = checkpoint_configuration.value["configuration_type"]
              min_pause_between_checkpoints = checkpoint_configuration.value["min_pause_between_checkpoints"]
            }
          }

          dynamic "monitoring_configuration" {
            for_each = flink_application_configuration.value.monitoring_configuration
            content {
              configuration_type = monitoring_configuration.value["configuration_type"]
              log_level          = monitoring_configuration.value["log_level"]
              metrics_level      = monitoring_configuration.value["metrics_level"]
            }
          }

          dynamic "parallelism_configuration" {
            for_each = flink_application_configuration.value.parallelism_configuration
            content {
              auto_scaling_enabled = parallelism_configuration.value["auto_scaling_enabled"]
              configuration_type   = parallelism_configuration.value["configuration_type"]
              parallelism          = parallelism_configuration.value["parallelism"]
              parallelism_per_kpu  = parallelism_configuration.value["parallelism_per_kpu"]
            }
          }

        }
      }

      dynamic "sql_application_configuration" {
        for_each = application_configuration.value.sql_application_configuration
        content {

          dynamic "input" {
            for_each = sql_application_configuration.value.input
            content {
              name_prefix = input.value["name_prefix"]

              dynamic "input_parallelism" {
                for_each = input.value.input_parallelism
                content {
                  count = input_parallelism.value["count"]
                }
              }

              dynamic "input_processing_configuration" {
                for_each = input.value.input_processing_configuration
                content {

                  dynamic "input_lambda_processor" {
                    for_each = input_processing_configuration.value.input_lambda_processor
                    content {
                      resource_arn = input_lambda_processor.value["resource_arn"]
                    }
                  }

                }
              }

              dynamic "input_schema" {
                for_each = input.value.input_schema
                content {
                  record_encoding = input_schema.value["record_encoding"]

                  dynamic "record_column" {
                    for_each = input_schema.value.record_column
                    content {
                      mapping  = record_column.value["mapping"]
                      name     = record_column.value["name"]
                      sql_type = record_column.value["sql_type"]
                    }
                  }

                  dynamic "record_format" {
                    for_each = input_schema.value.record_format
                    content {
                      record_format_type = record_format.value["record_format_type"]

                      dynamic "mapping_parameters" {
                        for_each = record_format.value.mapping_parameters
                        content {

                          dynamic "csv_mapping_parameters" {
                            for_each = mapping_parameters.value.csv_mapping_parameters
                            content {
                              record_column_delimiter = csv_mapping_parameters.value["record_column_delimiter"]
                              record_row_delimiter    = csv_mapping_parameters.value["record_row_delimiter"]
                            }
                          }

                          dynamic "json_mapping_parameters" {
                            for_each = mapping_parameters.value.json_mapping_parameters
                            content {
                              record_row_path = json_mapping_parameters.value["record_row_path"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "kinesis_firehose_input" {
                for_each = input.value.kinesis_firehose_input
                content {
                  resource_arn = kinesis_firehose_input.value["resource_arn"]
                }
              }

              dynamic "kinesis_streams_input" {
                for_each = input.value.kinesis_streams_input
                content {
                  resource_arn = kinesis_streams_input.value["resource_arn"]
                }
              }

            }
          }

          dynamic "output" {
            for_each = sql_application_configuration.value.output
            content {
              name = output.value["name"]

              dynamic "destination_schema" {
                for_each = output.value.destination_schema
                content {
                  record_format_type = destination_schema.value["record_format_type"]
                }
              }

              dynamic "kinesis_firehose_output" {
                for_each = output.value.kinesis_firehose_output
                content {
                  resource_arn = kinesis_firehose_output.value["resource_arn"]
                }
              }

              dynamic "kinesis_streams_output" {
                for_each = output.value.kinesis_streams_output
                content {
                  resource_arn = kinesis_streams_output.value["resource_arn"]
                }
              }

              dynamic "lambda_output" {
                for_each = output.value.lambda_output
                content {
                  resource_arn = lambda_output.value["resource_arn"]
                }
              }

            }
          }

          dynamic "reference_data_source" {
            for_each = sql_application_configuration.value.reference_data_source
            content {
              table_name = reference_data_source.value["table_name"]

              dynamic "reference_schema" {
                for_each = reference_data_source.value.reference_schema
                content {
                  record_encoding = reference_schema.value["record_encoding"]

                  dynamic "record_column" {
                    for_each = reference_schema.value.record_column
                    content {
                      mapping  = record_column.value["mapping"]
                      name     = record_column.value["name"]
                      sql_type = record_column.value["sql_type"]
                    }
                  }

                  dynamic "record_format" {
                    for_each = reference_schema.value.record_format
                    content {
                      record_format_type = record_format.value["record_format_type"]

                      dynamic "mapping_parameters" {
                        for_each = record_format.value.mapping_parameters
                        content {

                          dynamic "csv_mapping_parameters" {
                            for_each = mapping_parameters.value.csv_mapping_parameters
                            content {
                              record_column_delimiter = csv_mapping_parameters.value["record_column_delimiter"]
                              record_row_delimiter    = csv_mapping_parameters.value["record_row_delimiter"]
                            }
                          }

                          dynamic "json_mapping_parameters" {
                            for_each = mapping_parameters.value.json_mapping_parameters
                            content {
                              record_row_path = json_mapping_parameters.value["record_row_path"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "s3_reference_data_source" {
                for_each = reference_data_source.value.s3_reference_data_source
                content {
                  bucket_arn = s3_reference_data_source.value["bucket_arn"]
                  file_key   = s3_reference_data_source.value["file_key"]
                }
              }

            }
          }

        }
      }

      dynamic "vpc_configuration" {
        for_each = application_configuration.value.vpc_configuration
        content {
          security_group_ids = vpc_configuration.value["security_group_ids"]
          subnet_ids         = vpc_configuration.value["subnet_ids"]
        }
      }

    }
  }

  dynamic "cloudwatch_logging_options" {
    for_each = var.cloudwatch_logging_options
    content {
      log_stream_arn = cloudwatch_logging_options.value["log_stream_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_kinesisanalyticsv2_application.this.arn
}

output "create_timestamp" {
  description = "returns a string"
  value       = aws_kinesisanalyticsv2_application.this.create_timestamp
}

output "id" {
  description = "returns a string"
  value       = aws_kinesisanalyticsv2_application.this.id
}

output "last_update_timestamp" {
  description = "returns a string"
  value       = aws_kinesisanalyticsv2_application.this.last_update_timestamp
}

output "status" {
  description = "returns a string"
  value       = aws_kinesisanalyticsv2_application.this.status
}

output "version_id" {
  description = "returns a number"
  value       = aws_kinesisanalyticsv2_application.this.version_id
}

output "this" {
  value = aws_kinesisanalyticsv2_application.this
}
```

[top](#index)