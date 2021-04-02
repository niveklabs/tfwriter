# aws_glue_catalog_table

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
module "aws_glue_catalog_table" {
  source = "./modules/aws/r/aws_glue_catalog_table"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # database_name - (required) is a type of string
  database_name = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # owner - (optional) is a type of string
  owner = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # retention - (optional) is a type of number
  retention = null
  # table_type - (optional) is a type of string
  table_type = null
  # view_expanded_text - (optional) is a type of string
  view_expanded_text = null
  # view_original_text - (optional) is a type of string
  view_original_text = null

  partition_index = [{
    index_name   = null
    index_status = null
    keys         = []
  }]

  partition_keys = [{
    comment = null
    name    = null
    type    = null
  }]

  storage_descriptor = [{
    bucket_columns = []
    columns = [{
      comment    = null
      name       = null
      parameters = {}
      type       = null
    }]
    compressed        = null
    input_format      = null
    location          = null
    number_of_buckets = null
    output_format     = null
    parameters        = {}
    schema_reference = [{
      schema_id = [{
        registry_name = null
        schema_arn    = null
        schema_name   = null
      }]
      schema_version_id     = null
      schema_version_number = null
    }]
    ser_de_info = [{
      name                  = null
      parameters            = {}
      serialization_library = null
    }]
    skewed_info = [{
      skewed_column_names               = []
      skewed_column_value_location_maps = {}
      skewed_column_values              = []
    }]
    sort_columns = [{
      column     = null
      sort_order = null
    }]
    stored_as_sub_directories = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(required)"
  type        = string
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

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "retention" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "table_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "view_expanded_text" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "view_original_text" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "partition_index" {
  description = "nested block: NestingList, min items: 0, max items: 3"
  type = set(object(
    {
      index_name   = string
      index_status = string
      keys         = set(string)
    }
  ))
  default = []
}

variable "partition_keys" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment = string
      name    = string
      type    = string
    }
  ))
  default = []
}

variable "storage_descriptor" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_columns = list(string)
      columns = list(object(
        {
          comment    = string
          name       = string
          parameters = map(string)
          type       = string
        }
      ))
      compressed        = bool
      input_format      = string
      location          = string
      number_of_buckets = number
      output_format     = string
      parameters        = map(string)
      schema_reference = list(object(
        {
          schema_id = list(object(
            {
              registry_name = string
              schema_arn    = string
              schema_name   = string
            }
          ))
          schema_version_id     = string
          schema_version_number = number
        }
      ))
      ser_de_info = list(object(
        {
          name                  = string
          parameters            = map(string)
          serialization_library = string
        }
      ))
      skewed_info = list(object(
        {
          skewed_column_names               = list(string)
          skewed_column_value_location_maps = map(string)
          skewed_column_values              = list(string)
        }
      ))
      sort_columns = list(object(
        {
          column     = string
          sort_order = number
        }
      ))
      stored_as_sub_directories = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_catalog_table" "this" {
  catalog_id         = var.catalog_id
  database_name      = var.database_name
  description        = var.description
  name               = var.name
  owner              = var.owner
  parameters         = var.parameters
  retention          = var.retention
  table_type         = var.table_type
  view_expanded_text = var.view_expanded_text
  view_original_text = var.view_original_text

  dynamic "partition_index" {
    for_each = var.partition_index
    content {
      index_name = partition_index.value["index_name"]
      keys       = partition_index.value["keys"]
    }
  }

  dynamic "partition_keys" {
    for_each = var.partition_keys
    content {
      comment = partition_keys.value["comment"]
      name    = partition_keys.value["name"]
      type    = partition_keys.value["type"]
    }
  }

  dynamic "storage_descriptor" {
    for_each = var.storage_descriptor
    content {
      bucket_columns            = storage_descriptor.value["bucket_columns"]
      compressed                = storage_descriptor.value["compressed"]
      input_format              = storage_descriptor.value["input_format"]
      location                  = storage_descriptor.value["location"]
      number_of_buckets         = storage_descriptor.value["number_of_buckets"]
      output_format             = storage_descriptor.value["output_format"]
      parameters                = storage_descriptor.value["parameters"]
      stored_as_sub_directories = storage_descriptor.value["stored_as_sub_directories"]

      dynamic "columns" {
        for_each = storage_descriptor.value.columns
        content {
          comment    = columns.value["comment"]
          name       = columns.value["name"]
          parameters = columns.value["parameters"]
          type       = columns.value["type"]
        }
      }

      dynamic "schema_reference" {
        for_each = storage_descriptor.value.schema_reference
        content {
          schema_version_id     = schema_reference.value["schema_version_id"]
          schema_version_number = schema_reference.value["schema_version_number"]

          dynamic "schema_id" {
            for_each = schema_reference.value.schema_id
            content {
              registry_name = schema_id.value["registry_name"]
              schema_arn    = schema_id.value["schema_arn"]
              schema_name   = schema_id.value["schema_name"]
            }
          }

        }
      }

      dynamic "ser_de_info" {
        for_each = storage_descriptor.value.ser_de_info
        content {
          name                  = ser_de_info.value["name"]
          parameters            = ser_de_info.value["parameters"]
          serialization_library = ser_de_info.value["serialization_library"]
        }
      }

      dynamic "skewed_info" {
        for_each = storage_descriptor.value.skewed_info
        content {
          skewed_column_names               = skewed_info.value["skewed_column_names"]
          skewed_column_value_location_maps = skewed_info.value["skewed_column_value_location_maps"]
          skewed_column_values              = skewed_info.value["skewed_column_values"]
        }
      }

      dynamic "sort_columns" {
        for_each = storage_descriptor.value.sort_columns
        content {
          column     = sort_columns.value["column"]
          sort_order = sort_columns.value["sort_order"]
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
  value       = aws_glue_catalog_table.this.arn
}

output "catalog_id" {
  description = "returns a string"
  value       = aws_glue_catalog_table.this.catalog_id
}

output "id" {
  description = "returns a string"
  value       = aws_glue_catalog_table.this.id
}

output "this" {
  value = aws_glue_catalog_table.this
}
```

[top](#index)