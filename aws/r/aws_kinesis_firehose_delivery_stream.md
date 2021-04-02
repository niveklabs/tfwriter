# aws_kinesis_firehose_delivery_stream

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
module "aws_kinesis_firehose_delivery_stream" {
  source = "./modules/aws/r/aws_kinesis_firehose_delivery_stream"

  # arn - (optional) is a type of string
  arn = null
  # destination - (required) is a type of string
  destination = null
  # destination_id - (optional) is a type of string
  destination_id = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version_id - (optional) is a type of string
  version_id = null

  elasticsearch_configuration = [{
    buffering_interval = null
    buffering_size     = null
    cloudwatch_logging_options = [{
      enabled         = null
      log_group_name  = null
      log_stream_name = null
    }]
    cluster_endpoint      = null
    domain_arn            = null
    index_name            = null
    index_rotation_period = null
    processing_configuration = [{
      enabled = null
      processors = [{
        parameters = [{
          parameter_name  = null
          parameter_value = null
        }]
        type = null
      }]
    }]
    retry_duration = null
    role_arn       = null
    s3_backup_mode = null
    type_name      = null
    vpc_config = [{
      role_arn           = null
      security_group_ids = []
      subnet_ids         = []
      vpc_id             = null
    }]
  }]

  extended_s3_configuration = [{
    bucket_arn      = null
    buffer_interval = null
    buffer_size     = null
    cloudwatch_logging_options = [{
      enabled         = null
      log_group_name  = null
      log_stream_name = null
    }]
    compression_format = null
    data_format_conversion_configuration = [{
      enabled = null
      input_format_configuration = [{
        deserializer = [{
          hive_json_ser_de = [{
            timestamp_formats = []
          }]
          open_x_json_ser_de = [{
            case_insensitive                         = null
            column_to_json_key_mappings              = {}
            convert_dots_in_json_keys_to_underscores = null
          }]
        }]
      }]
      output_format_configuration = [{
        serializer = [{
          orc_ser_de = [{
            block_size_bytes                        = null
            bloom_filter_columns                    = []
            bloom_filter_false_positive_probability = null
            compression                             = null
            dictionary_key_threshold                = null
            enable_padding                          = null
            format_version                          = null
            padding_tolerance                       = null
            row_index_stride                        = null
            stripe_size_bytes                       = null
          }]
          parquet_ser_de = [{
            block_size_bytes              = null
            compression                   = null
            enable_dictionary_compression = null
            max_padding_bytes             = null
            page_size_bytes               = null
            writer_version                = null
          }]
        }]
      }]
      schema_configuration = [{
        catalog_id    = null
        database_name = null
        region        = null
        role_arn      = null
        table_name    = null
        version_id    = null
      }]
    }]
    error_output_prefix = null
    kms_key_arn         = null
    prefix              = null
    processing_configuration = [{
      enabled = null
      processors = [{
        parameters = [{
          parameter_name  = null
          parameter_value = null
        }]
        type = null
      }]
    }]
    role_arn = null
    s3_backup_configuration = [{
      bucket_arn      = null
      buffer_interval = null
      buffer_size     = null
      cloudwatch_logging_options = [{
        enabled         = null
        log_group_name  = null
        log_stream_name = null
      }]
      compression_format = null
      kms_key_arn        = null
      prefix             = null
      role_arn           = null
    }]
    s3_backup_mode = null
  }]

  http_endpoint_configuration = [{
    access_key         = null
    buffering_interval = null
    buffering_size     = null
    cloudwatch_logging_options = [{
      enabled         = null
      log_group_name  = null
      log_stream_name = null
    }]
    name = null
    processing_configuration = [{
      enabled = null
      processors = [{
        parameters = [{
          parameter_name  = null
          parameter_value = null
        }]
        type = null
      }]
    }]
    request_configuration = [{
      common_attributes = [{
        name  = null
        value = null
      }]
      content_encoding = null
    }]
    retry_duration = null
    role_arn       = null
    s3_backup_mode = null
    url            = null
  }]

  kinesis_source_configuration = [{
    kinesis_stream_arn = null
    role_arn           = null
  }]

  redshift_configuration = [{
    cloudwatch_logging_options = [{
      enabled         = null
      log_group_name  = null
      log_stream_name = null
    }]
    cluster_jdbcurl    = null
    copy_options       = null
    data_table_columns = null
    data_table_name    = null
    password           = null
    processing_configuration = [{
      enabled = null
      processors = [{
        parameters = [{
          parameter_name  = null
          parameter_value = null
        }]
        type = null
      }]
    }]
    retry_duration = null
    role_arn       = null
    s3_backup_configuration = [{
      bucket_arn      = null
      buffer_interval = null
      buffer_size     = null
      cloudwatch_logging_options = [{
        enabled         = null
        log_group_name  = null
        log_stream_name = null
      }]
      compression_format = null
      kms_key_arn        = null
      prefix             = null
      role_arn           = null
    }]
    s3_backup_mode = null
    username       = null
  }]

  s3_configuration = [{
    bucket_arn      = null
    buffer_interval = null
    buffer_size     = null
    cloudwatch_logging_options = [{
      enabled         = null
      log_group_name  = null
      log_stream_name = null
    }]
    compression_format = null
    kms_key_arn        = null
    prefix             = null
    role_arn           = null
  }]

  server_side_encryption = [{
    enabled  = null
    key_arn  = null
    key_type = null
  }]

  splunk_configuration = [{
    cloudwatch_logging_options = [{
      enabled         = null
      log_group_name  = null
      log_stream_name = null
    }]
    hec_acknowledgment_timeout = null
    hec_endpoint               = null
    hec_endpoint_type          = null
    hec_token                  = null
    processing_configuration = [{
      enabled = null
      processors = [{
        parameters = [{
          parameter_name  = null
          parameter_value = null
        }]
        type = null
      }]
    }]
    retry_duration = null
    s3_backup_mode = null
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

variable "destination" {
  description = "(required)"
  type        = string
}

variable "destination_id" {
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

variable "version_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elasticsearch_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      buffering_interval = number
      buffering_size     = number
      cloudwatch_logging_options = list(object(
        {
          enabled         = bool
          log_group_name  = string
          log_stream_name = string
        }
      ))
      cluster_endpoint      = string
      domain_arn            = string
      index_name            = string
      index_rotation_period = string
      processing_configuration = list(object(
        {
          enabled = bool
          processors = list(object(
            {
              parameters = list(object(
                {
                  parameter_name  = string
                  parameter_value = string
                }
              ))
              type = string
            }
          ))
        }
      ))
      retry_duration = number
      role_arn       = string
      s3_backup_mode = string
      type_name      = string
      vpc_config = list(object(
        {
          role_arn           = string
          security_group_ids = set(string)
          subnet_ids         = set(string)
          vpc_id             = string
        }
      ))
    }
  ))
  default = []
}

variable "extended_s3_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_arn      = string
      buffer_interval = number
      buffer_size     = number
      cloudwatch_logging_options = list(object(
        {
          enabled         = bool
          log_group_name  = string
          log_stream_name = string
        }
      ))
      compression_format = string
      data_format_conversion_configuration = list(object(
        {
          enabled = bool
          input_format_configuration = list(object(
            {
              deserializer = list(object(
                {
                  hive_json_ser_de = list(object(
                    {
                      timestamp_formats = list(string)
                    }
                  ))
                  open_x_json_ser_de = list(object(
                    {
                      case_insensitive                         = bool
                      column_to_json_key_mappings              = map(string)
                      convert_dots_in_json_keys_to_underscores = bool
                    }
                  ))
                }
              ))
            }
          ))
          output_format_configuration = list(object(
            {
              serializer = list(object(
                {
                  orc_ser_de = list(object(
                    {
                      block_size_bytes                        = number
                      bloom_filter_columns                    = list(string)
                      bloom_filter_false_positive_probability = number
                      compression                             = string
                      dictionary_key_threshold                = number
                      enable_padding                          = bool
                      format_version                          = string
                      padding_tolerance                       = number
                      row_index_stride                        = number
                      stripe_size_bytes                       = number
                    }
                  ))
                  parquet_ser_de = list(object(
                    {
                      block_size_bytes              = number
                      compression                   = string
                      enable_dictionary_compression = bool
                      max_padding_bytes             = number
                      page_size_bytes               = number
                      writer_version                = string
                    }
                  ))
                }
              ))
            }
          ))
          schema_configuration = list(object(
            {
              catalog_id    = string
              database_name = string
              region        = string
              role_arn      = string
              table_name    = string
              version_id    = string
            }
          ))
        }
      ))
      error_output_prefix = string
      kms_key_arn         = string
      prefix              = string
      processing_configuration = list(object(
        {
          enabled = bool
          processors = list(object(
            {
              parameters = list(object(
                {
                  parameter_name  = string
                  parameter_value = string
                }
              ))
              type = string
            }
          ))
        }
      ))
      role_arn = string
      s3_backup_configuration = list(object(
        {
          bucket_arn      = string
          buffer_interval = number
          buffer_size     = number
          cloudwatch_logging_options = list(object(
            {
              enabled         = bool
              log_group_name  = string
              log_stream_name = string
            }
          ))
          compression_format = string
          kms_key_arn        = string
          prefix             = string
          role_arn           = string
        }
      ))
      s3_backup_mode = string
    }
  ))
  default = []
}

variable "http_endpoint_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key         = string
      buffering_interval = number
      buffering_size     = number
      cloudwatch_logging_options = list(object(
        {
          enabled         = bool
          log_group_name  = string
          log_stream_name = string
        }
      ))
      name = string
      processing_configuration = list(object(
        {
          enabled = bool
          processors = list(object(
            {
              parameters = list(object(
                {
                  parameter_name  = string
                  parameter_value = string
                }
              ))
              type = string
            }
          ))
        }
      ))
      request_configuration = list(object(
        {
          common_attributes = list(object(
            {
              name  = string
              value = string
            }
          ))
          content_encoding = string
        }
      ))
      retry_duration = number
      role_arn       = string
      s3_backup_mode = string
      url            = string
    }
  ))
  default = []
}

variable "kinesis_source_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kinesis_stream_arn = string
      role_arn           = string
    }
  ))
  default = []
}

variable "redshift_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudwatch_logging_options = list(object(
        {
          enabled         = bool
          log_group_name  = string
          log_stream_name = string
        }
      ))
      cluster_jdbcurl    = string
      copy_options       = string
      data_table_columns = string
      data_table_name    = string
      password           = string
      processing_configuration = list(object(
        {
          enabled = bool
          processors = list(object(
            {
              parameters = list(object(
                {
                  parameter_name  = string
                  parameter_value = string
                }
              ))
              type = string
            }
          ))
        }
      ))
      retry_duration = number
      role_arn       = string
      s3_backup_configuration = list(object(
        {
          bucket_arn      = string
          buffer_interval = number
          buffer_size     = number
          cloudwatch_logging_options = list(object(
            {
              enabled         = bool
              log_group_name  = string
              log_stream_name = string
            }
          ))
          compression_format = string
          kms_key_arn        = string
          prefix             = string
          role_arn           = string
        }
      ))
      s3_backup_mode = string
      username       = string
    }
  ))
  default = []
}

variable "s3_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_arn      = string
      buffer_interval = number
      buffer_size     = number
      cloudwatch_logging_options = list(object(
        {
          enabled         = bool
          log_group_name  = string
          log_stream_name = string
        }
      ))
      compression_format = string
      kms_key_arn        = string
      prefix             = string
      role_arn           = string
    }
  ))
  default = []
}

variable "server_side_encryption" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled  = bool
      key_arn  = string
      key_type = string
    }
  ))
  default = []
}

variable "splunk_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudwatch_logging_options = list(object(
        {
          enabled         = bool
          log_group_name  = string
          log_stream_name = string
        }
      ))
      hec_acknowledgment_timeout = number
      hec_endpoint               = string
      hec_endpoint_type          = string
      hec_token                  = string
      processing_configuration = list(object(
        {
          enabled = bool
          processors = list(object(
            {
              parameters = list(object(
                {
                  parameter_name  = string
                  parameter_value = string
                }
              ))
              type = string
            }
          ))
        }
      ))
      retry_duration = number
      s3_backup_mode = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_kinesis_firehose_delivery_stream" "this" {
  arn            = var.arn
  destination    = var.destination
  destination_id = var.destination_id
  name           = var.name
  tags           = var.tags
  version_id     = var.version_id

  dynamic "elasticsearch_configuration" {
    for_each = var.elasticsearch_configuration
    content {
      buffering_interval    = elasticsearch_configuration.value["buffering_interval"]
      buffering_size        = elasticsearch_configuration.value["buffering_size"]
      cluster_endpoint      = elasticsearch_configuration.value["cluster_endpoint"]
      domain_arn            = elasticsearch_configuration.value["domain_arn"]
      index_name            = elasticsearch_configuration.value["index_name"]
      index_rotation_period = elasticsearch_configuration.value["index_rotation_period"]
      retry_duration        = elasticsearch_configuration.value["retry_duration"]
      role_arn              = elasticsearch_configuration.value["role_arn"]
      s3_backup_mode        = elasticsearch_configuration.value["s3_backup_mode"]
      type_name             = elasticsearch_configuration.value["type_name"]

      dynamic "cloudwatch_logging_options" {
        for_each = elasticsearch_configuration.value.cloudwatch_logging_options
        content {
          enabled         = cloudwatch_logging_options.value["enabled"]
          log_group_name  = cloudwatch_logging_options.value["log_group_name"]
          log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
        }
      }

      dynamic "processing_configuration" {
        for_each = elasticsearch_configuration.value.processing_configuration
        content {
          enabled = processing_configuration.value["enabled"]

          dynamic "processors" {
            for_each = processing_configuration.value.processors
            content {
              type = processors.value["type"]

              dynamic "parameters" {
                for_each = processors.value.parameters
                content {
                  parameter_name  = parameters.value["parameter_name"]
                  parameter_value = parameters.value["parameter_value"]
                }
              }

            }
          }

        }
      }

      dynamic "vpc_config" {
        for_each = elasticsearch_configuration.value.vpc_config
        content {
          role_arn           = vpc_config.value["role_arn"]
          security_group_ids = vpc_config.value["security_group_ids"]
          subnet_ids         = vpc_config.value["subnet_ids"]
        }
      }

    }
  }

  dynamic "extended_s3_configuration" {
    for_each = var.extended_s3_configuration
    content {
      bucket_arn          = extended_s3_configuration.value["bucket_arn"]
      buffer_interval     = extended_s3_configuration.value["buffer_interval"]
      buffer_size         = extended_s3_configuration.value["buffer_size"]
      compression_format  = extended_s3_configuration.value["compression_format"]
      error_output_prefix = extended_s3_configuration.value["error_output_prefix"]
      kms_key_arn         = extended_s3_configuration.value["kms_key_arn"]
      prefix              = extended_s3_configuration.value["prefix"]
      role_arn            = extended_s3_configuration.value["role_arn"]
      s3_backup_mode      = extended_s3_configuration.value["s3_backup_mode"]

      dynamic "cloudwatch_logging_options" {
        for_each = extended_s3_configuration.value.cloudwatch_logging_options
        content {
          enabled         = cloudwatch_logging_options.value["enabled"]
          log_group_name  = cloudwatch_logging_options.value["log_group_name"]
          log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
        }
      }

      dynamic "data_format_conversion_configuration" {
        for_each = extended_s3_configuration.value.data_format_conversion_configuration
        content {
          enabled = data_format_conversion_configuration.value["enabled"]

          dynamic "input_format_configuration" {
            for_each = data_format_conversion_configuration.value.input_format_configuration
            content {

              dynamic "deserializer" {
                for_each = input_format_configuration.value.deserializer
                content {

                  dynamic "hive_json_ser_de" {
                    for_each = deserializer.value.hive_json_ser_de
                    content {
                      timestamp_formats = hive_json_ser_de.value["timestamp_formats"]
                    }
                  }

                  dynamic "open_x_json_ser_de" {
                    for_each = deserializer.value.open_x_json_ser_de
                    content {
                      case_insensitive                         = open_x_json_ser_de.value["case_insensitive"]
                      column_to_json_key_mappings              = open_x_json_ser_de.value["column_to_json_key_mappings"]
                      convert_dots_in_json_keys_to_underscores = open_x_json_ser_de.value["convert_dots_in_json_keys_to_underscores"]
                    }
                  }

                }
              }

            }
          }

          dynamic "output_format_configuration" {
            for_each = data_format_conversion_configuration.value.output_format_configuration
            content {

              dynamic "serializer" {
                for_each = output_format_configuration.value.serializer
                content {

                  dynamic "orc_ser_de" {
                    for_each = serializer.value.orc_ser_de
                    content {
                      block_size_bytes                        = orc_ser_de.value["block_size_bytes"]
                      bloom_filter_columns                    = orc_ser_de.value["bloom_filter_columns"]
                      bloom_filter_false_positive_probability = orc_ser_de.value["bloom_filter_false_positive_probability"]
                      compression                             = orc_ser_de.value["compression"]
                      dictionary_key_threshold                = orc_ser_de.value["dictionary_key_threshold"]
                      enable_padding                          = orc_ser_de.value["enable_padding"]
                      format_version                          = orc_ser_de.value["format_version"]
                      padding_tolerance                       = orc_ser_de.value["padding_tolerance"]
                      row_index_stride                        = orc_ser_de.value["row_index_stride"]
                      stripe_size_bytes                       = orc_ser_de.value["stripe_size_bytes"]
                    }
                  }

                  dynamic "parquet_ser_de" {
                    for_each = serializer.value.parquet_ser_de
                    content {
                      block_size_bytes              = parquet_ser_de.value["block_size_bytes"]
                      compression                   = parquet_ser_de.value["compression"]
                      enable_dictionary_compression = parquet_ser_de.value["enable_dictionary_compression"]
                      max_padding_bytes             = parquet_ser_de.value["max_padding_bytes"]
                      page_size_bytes               = parquet_ser_de.value["page_size_bytes"]
                      writer_version                = parquet_ser_de.value["writer_version"]
                    }
                  }

                }
              }

            }
          }

          dynamic "schema_configuration" {
            for_each = data_format_conversion_configuration.value.schema_configuration
            content {
              catalog_id    = schema_configuration.value["catalog_id"]
              database_name = schema_configuration.value["database_name"]
              region        = schema_configuration.value["region"]
              role_arn      = schema_configuration.value["role_arn"]
              table_name    = schema_configuration.value["table_name"]
              version_id    = schema_configuration.value["version_id"]
            }
          }

        }
      }

      dynamic "processing_configuration" {
        for_each = extended_s3_configuration.value.processing_configuration
        content {
          enabled = processing_configuration.value["enabled"]

          dynamic "processors" {
            for_each = processing_configuration.value.processors
            content {
              type = processors.value["type"]

              dynamic "parameters" {
                for_each = processors.value.parameters
                content {
                  parameter_name  = parameters.value["parameter_name"]
                  parameter_value = parameters.value["parameter_value"]
                }
              }

            }
          }

        }
      }

      dynamic "s3_backup_configuration" {
        for_each = extended_s3_configuration.value.s3_backup_configuration
        content {
          bucket_arn         = s3_backup_configuration.value["bucket_arn"]
          buffer_interval    = s3_backup_configuration.value["buffer_interval"]
          buffer_size        = s3_backup_configuration.value["buffer_size"]
          compression_format = s3_backup_configuration.value["compression_format"]
          kms_key_arn        = s3_backup_configuration.value["kms_key_arn"]
          prefix             = s3_backup_configuration.value["prefix"]
          role_arn           = s3_backup_configuration.value["role_arn"]

          dynamic "cloudwatch_logging_options" {
            for_each = s3_backup_configuration.value.cloudwatch_logging_options
            content {
              enabled         = cloudwatch_logging_options.value["enabled"]
              log_group_name  = cloudwatch_logging_options.value["log_group_name"]
              log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
            }
          }

        }
      }

    }
  }

  dynamic "http_endpoint_configuration" {
    for_each = var.http_endpoint_configuration
    content {
      access_key         = http_endpoint_configuration.value["access_key"]
      buffering_interval = http_endpoint_configuration.value["buffering_interval"]
      buffering_size     = http_endpoint_configuration.value["buffering_size"]
      name               = http_endpoint_configuration.value["name"]
      retry_duration     = http_endpoint_configuration.value["retry_duration"]
      role_arn           = http_endpoint_configuration.value["role_arn"]
      s3_backup_mode     = http_endpoint_configuration.value["s3_backup_mode"]
      url                = http_endpoint_configuration.value["url"]

      dynamic "cloudwatch_logging_options" {
        for_each = http_endpoint_configuration.value.cloudwatch_logging_options
        content {
          enabled         = cloudwatch_logging_options.value["enabled"]
          log_group_name  = cloudwatch_logging_options.value["log_group_name"]
          log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
        }
      }

      dynamic "processing_configuration" {
        for_each = http_endpoint_configuration.value.processing_configuration
        content {
          enabled = processing_configuration.value["enabled"]

          dynamic "processors" {
            for_each = processing_configuration.value.processors
            content {
              type = processors.value["type"]

              dynamic "parameters" {
                for_each = processors.value.parameters
                content {
                  parameter_name  = parameters.value["parameter_name"]
                  parameter_value = parameters.value["parameter_value"]
                }
              }

            }
          }

        }
      }

      dynamic "request_configuration" {
        for_each = http_endpoint_configuration.value.request_configuration
        content {
          content_encoding = request_configuration.value["content_encoding"]

          dynamic "common_attributes" {
            for_each = request_configuration.value.common_attributes
            content {
              name  = common_attributes.value["name"]
              value = common_attributes.value["value"]
            }
          }

        }
      }

    }
  }

  dynamic "kinesis_source_configuration" {
    for_each = var.kinesis_source_configuration
    content {
      kinesis_stream_arn = kinesis_source_configuration.value["kinesis_stream_arn"]
      role_arn           = kinesis_source_configuration.value["role_arn"]
    }
  }

  dynamic "redshift_configuration" {
    for_each = var.redshift_configuration
    content {
      cluster_jdbcurl    = redshift_configuration.value["cluster_jdbcurl"]
      copy_options       = redshift_configuration.value["copy_options"]
      data_table_columns = redshift_configuration.value["data_table_columns"]
      data_table_name    = redshift_configuration.value["data_table_name"]
      password           = redshift_configuration.value["password"]
      retry_duration     = redshift_configuration.value["retry_duration"]
      role_arn           = redshift_configuration.value["role_arn"]
      s3_backup_mode     = redshift_configuration.value["s3_backup_mode"]
      username           = redshift_configuration.value["username"]

      dynamic "cloudwatch_logging_options" {
        for_each = redshift_configuration.value.cloudwatch_logging_options
        content {
          enabled         = cloudwatch_logging_options.value["enabled"]
          log_group_name  = cloudwatch_logging_options.value["log_group_name"]
          log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
        }
      }

      dynamic "processing_configuration" {
        for_each = redshift_configuration.value.processing_configuration
        content {
          enabled = processing_configuration.value["enabled"]

          dynamic "processors" {
            for_each = processing_configuration.value.processors
            content {
              type = processors.value["type"]

              dynamic "parameters" {
                for_each = processors.value.parameters
                content {
                  parameter_name  = parameters.value["parameter_name"]
                  parameter_value = parameters.value["parameter_value"]
                }
              }

            }
          }

        }
      }

      dynamic "s3_backup_configuration" {
        for_each = redshift_configuration.value.s3_backup_configuration
        content {
          bucket_arn         = s3_backup_configuration.value["bucket_arn"]
          buffer_interval    = s3_backup_configuration.value["buffer_interval"]
          buffer_size        = s3_backup_configuration.value["buffer_size"]
          compression_format = s3_backup_configuration.value["compression_format"]
          kms_key_arn        = s3_backup_configuration.value["kms_key_arn"]
          prefix             = s3_backup_configuration.value["prefix"]
          role_arn           = s3_backup_configuration.value["role_arn"]

          dynamic "cloudwatch_logging_options" {
            for_each = s3_backup_configuration.value.cloudwatch_logging_options
            content {
              enabled         = cloudwatch_logging_options.value["enabled"]
              log_group_name  = cloudwatch_logging_options.value["log_group_name"]
              log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
            }
          }

        }
      }

    }
  }

  dynamic "s3_configuration" {
    for_each = var.s3_configuration
    content {
      bucket_arn         = s3_configuration.value["bucket_arn"]
      buffer_interval    = s3_configuration.value["buffer_interval"]
      buffer_size        = s3_configuration.value["buffer_size"]
      compression_format = s3_configuration.value["compression_format"]
      kms_key_arn        = s3_configuration.value["kms_key_arn"]
      prefix             = s3_configuration.value["prefix"]
      role_arn           = s3_configuration.value["role_arn"]

      dynamic "cloudwatch_logging_options" {
        for_each = s3_configuration.value.cloudwatch_logging_options
        content {
          enabled         = cloudwatch_logging_options.value["enabled"]
          log_group_name  = cloudwatch_logging_options.value["log_group_name"]
          log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
        }
      }

    }
  }

  dynamic "server_side_encryption" {
    for_each = var.server_side_encryption
    content {
      enabled  = server_side_encryption.value["enabled"]
      key_arn  = server_side_encryption.value["key_arn"]
      key_type = server_side_encryption.value["key_type"]
    }
  }

  dynamic "splunk_configuration" {
    for_each = var.splunk_configuration
    content {
      hec_acknowledgment_timeout = splunk_configuration.value["hec_acknowledgment_timeout"]
      hec_endpoint               = splunk_configuration.value["hec_endpoint"]
      hec_endpoint_type          = splunk_configuration.value["hec_endpoint_type"]
      hec_token                  = splunk_configuration.value["hec_token"]
      retry_duration             = splunk_configuration.value["retry_duration"]
      s3_backup_mode             = splunk_configuration.value["s3_backup_mode"]

      dynamic "cloudwatch_logging_options" {
        for_each = splunk_configuration.value.cloudwatch_logging_options
        content {
          enabled         = cloudwatch_logging_options.value["enabled"]
          log_group_name  = cloudwatch_logging_options.value["log_group_name"]
          log_stream_name = cloudwatch_logging_options.value["log_stream_name"]
        }
      }

      dynamic "processing_configuration" {
        for_each = splunk_configuration.value.processing_configuration
        content {
          enabled = processing_configuration.value["enabled"]

          dynamic "processors" {
            for_each = processing_configuration.value.processors
            content {
              type = processors.value["type"]

              dynamic "parameters" {
                for_each = processors.value.parameters
                content {
                  parameter_name  = parameters.value["parameter_name"]
                  parameter_value = parameters.value["parameter_value"]
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
  value       = aws_kinesis_firehose_delivery_stream.this.arn
}

output "destination_id" {
  description = "returns a string"
  value       = aws_kinesis_firehose_delivery_stream.this.destination_id
}

output "id" {
  description = "returns a string"
  value       = aws_kinesis_firehose_delivery_stream.this.id
}

output "version_id" {
  description = "returns a string"
  value       = aws_kinesis_firehose_delivery_stream.this.version_id
}

output "this" {
  value = aws_kinesis_firehose_delivery_stream.this
}
```

[top](#index)