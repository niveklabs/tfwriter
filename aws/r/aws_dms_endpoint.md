# aws_dms_endpoint

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
module "aws_dms_endpoint" {
  source = "./modules/aws/r/aws_dms_endpoint"

  # certificate_arn - (optional) is a type of string
  certificate_arn = null
  # database_name - (optional) is a type of string
  database_name = null
  # endpoint_id - (required) is a type of string
  endpoint_id = null
  # endpoint_type - (required) is a type of string
  endpoint_type = null
  # engine_name - (required) is a type of string
  engine_name = null
  # extra_connection_attributes - (optional) is a type of string
  extra_connection_attributes = null
  # kms_key_arn - (optional) is a type of string
  kms_key_arn = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # server_name - (optional) is a type of string
  server_name = null
  # service_access_role - (optional) is a type of string
  service_access_role = null
  # ssl_mode - (optional) is a type of string
  ssl_mode = null
  # tags - (optional) is a type of map of string
  tags = {}
  # username - (optional) is a type of string
  username = null

  elasticsearch_settings = [{
    endpoint_uri               = null
    error_retry_duration       = null
    full_load_error_percentage = null
    service_access_role_arn    = null
  }]

  kafka_settings = [{
    broker = null
    topic  = null
  }]

  kinesis_settings = [{
    message_format          = null
    service_access_role_arn = null
    stream_arn              = null
  }]

  mongodb_settings = [{
    auth_mechanism      = null
    auth_source         = null
    auth_type           = null
    docs_to_investigate = null
    extract_doc_id      = null
    nesting_level       = null
  }]

  s3_settings = [{
    bucket_folder             = null
    bucket_name               = null
    compression_type          = null
    csv_delimiter             = null
    csv_row_delimiter         = null
    external_table_definition = null
    service_access_role_arn   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_id" {
  description = "(required)"
  type        = string
}

variable "endpoint_type" {
  description = "(required)"
  type        = string
}

variable "engine_name" {
  description = "(required)"
  type        = string
}

variable "extra_connection_attributes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_access_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elasticsearch_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      endpoint_uri               = string
      error_retry_duration       = number
      full_load_error_percentage = number
      service_access_role_arn    = string
    }
  ))
  default = []
}

variable "kafka_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      broker = string
      topic  = string
    }
  ))
  default = []
}

variable "kinesis_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      message_format          = string
      service_access_role_arn = string
      stream_arn              = string
    }
  ))
  default = []
}

variable "mongodb_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_mechanism      = string
      auth_source         = string
      auth_type           = string
      docs_to_investigate = string
      extract_doc_id      = string
      nesting_level       = string
    }
  ))
  default = []
}

variable "s3_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_folder             = string
      bucket_name               = string
      compression_type          = string
      csv_delimiter             = string
      csv_row_delimiter         = string
      external_table_definition = string
      service_access_role_arn   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dms_endpoint" "this" {
  certificate_arn             = var.certificate_arn
  database_name               = var.database_name
  endpoint_id                 = var.endpoint_id
  endpoint_type               = var.endpoint_type
  engine_name                 = var.engine_name
  extra_connection_attributes = var.extra_connection_attributes
  kms_key_arn                 = var.kms_key_arn
  password                    = var.password
  port                        = var.port
  server_name                 = var.server_name
  service_access_role         = var.service_access_role
  ssl_mode                    = var.ssl_mode
  tags                        = var.tags
  username                    = var.username

  dynamic "elasticsearch_settings" {
    for_each = var.elasticsearch_settings
    content {
      endpoint_uri               = elasticsearch_settings.value["endpoint_uri"]
      error_retry_duration       = elasticsearch_settings.value["error_retry_duration"]
      full_load_error_percentage = elasticsearch_settings.value["full_load_error_percentage"]
      service_access_role_arn    = elasticsearch_settings.value["service_access_role_arn"]
    }
  }

  dynamic "kafka_settings" {
    for_each = var.kafka_settings
    content {
      broker = kafka_settings.value["broker"]
      topic  = kafka_settings.value["topic"]
    }
  }

  dynamic "kinesis_settings" {
    for_each = var.kinesis_settings
    content {
      message_format          = kinesis_settings.value["message_format"]
      service_access_role_arn = kinesis_settings.value["service_access_role_arn"]
      stream_arn              = kinesis_settings.value["stream_arn"]
    }
  }

  dynamic "mongodb_settings" {
    for_each = var.mongodb_settings
    content {
      auth_mechanism      = mongodb_settings.value["auth_mechanism"]
      auth_source         = mongodb_settings.value["auth_source"]
      auth_type           = mongodb_settings.value["auth_type"]
      docs_to_investigate = mongodb_settings.value["docs_to_investigate"]
      extract_doc_id      = mongodb_settings.value["extract_doc_id"]
      nesting_level       = mongodb_settings.value["nesting_level"]
    }
  }

  dynamic "s3_settings" {
    for_each = var.s3_settings
    content {
      bucket_folder             = s3_settings.value["bucket_folder"]
      bucket_name               = s3_settings.value["bucket_name"]
      compression_type          = s3_settings.value["compression_type"]
      csv_delimiter             = s3_settings.value["csv_delimiter"]
      csv_row_delimiter         = s3_settings.value["csv_row_delimiter"]
      external_table_definition = s3_settings.value["external_table_definition"]
      service_access_role_arn   = s3_settings.value["service_access_role_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate_arn" {
  description = "returns a string"
  value       = aws_dms_endpoint.this.certificate_arn
}

output "endpoint_arn" {
  description = "returns a string"
  value       = aws_dms_endpoint.this.endpoint_arn
}

output "extra_connection_attributes" {
  description = "returns a string"
  value       = aws_dms_endpoint.this.extra_connection_attributes
}

output "id" {
  description = "returns a string"
  value       = aws_dms_endpoint.this.id
}

output "kms_key_arn" {
  description = "returns a string"
  value       = aws_dms_endpoint.this.kms_key_arn
}

output "ssl_mode" {
  description = "returns a string"
  value       = aws_dms_endpoint.this.ssl_mode
}

output "this" {
  value = aws_dms_endpoint.this
}
```

[top](#index)