# aws_glue_partition

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
module "aws_glue_partition" {
  source = "./modules/aws/r/aws_glue_partition"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # database_name - (required) is a type of string
  database_name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # partition_values - (required) is a type of list of string
  partition_values = []
  # table_name - (required) is a type of string
  table_name = null

  storage_descriptor = [{
    bucket_columns = []
    columns = [{
      comment = null
      name    = null
      type    = null
    }]
    compressed        = null
    input_format      = null
    location          = null
    number_of_buckets = null
    output_format     = null
    parameters        = {}
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

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "partition_values" {
  description = "(required)"
  type        = list(string)
}

variable "table_name" {
  description = "(required)"
  type        = string
}

variable "storage_descriptor" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_columns = list(string)
      columns = list(object(
        {
          comment = string
          name    = string
          type    = string
        }
      ))
      compressed        = bool
      input_format      = string
      location          = string
      number_of_buckets = number
      output_format     = string
      parameters        = map(string)
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
resource "aws_glue_partition" "this" {
  # catalog_id - (optional) is a type of string
  catalog_id = var.catalog_id
  # database_name - (required) is a type of string
  database_name = var.database_name
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # partition_values - (required) is a type of list of string
  partition_values = var.partition_values
  # table_name - (required) is a type of string
  table_name = var.table_name

  dynamic "storage_descriptor" {
    for_each = var.storage_descriptor
    content {
      # bucket_columns - (optional) is a type of list of string
      bucket_columns = storage_descriptor.value["bucket_columns"]
      # compressed - (optional) is a type of bool
      compressed = storage_descriptor.value["compressed"]
      # input_format - (optional) is a type of string
      input_format = storage_descriptor.value["input_format"]
      # location - (optional) is a type of string
      location = storage_descriptor.value["location"]
      # number_of_buckets - (optional) is a type of number
      number_of_buckets = storage_descriptor.value["number_of_buckets"]
      # output_format - (optional) is a type of string
      output_format = storage_descriptor.value["output_format"]
      # parameters - (optional) is a type of map of string
      parameters = storage_descriptor.value["parameters"]
      # stored_as_sub_directories - (optional) is a type of bool
      stored_as_sub_directories = storage_descriptor.value["stored_as_sub_directories"]

      dynamic "columns" {
        for_each = storage_descriptor.value.columns
        content {
          # comment - (optional) is a type of string
          comment = columns.value["comment"]
          # name - (required) is a type of string
          name = columns.value["name"]
          # type - (optional) is a type of string
          type = columns.value["type"]
        }
      }

      dynamic "ser_de_info" {
        for_each = storage_descriptor.value.ser_de_info
        content {
          # name - (optional) is a type of string
          name = ser_de_info.value["name"]
          # parameters - (optional) is a type of map of string
          parameters = ser_de_info.value["parameters"]
          # serialization_library - (optional) is a type of string
          serialization_library = ser_de_info.value["serialization_library"]
        }
      }

      dynamic "skewed_info" {
        for_each = storage_descriptor.value.skewed_info
        content {
          # skewed_column_names - (optional) is a type of list of string
          skewed_column_names = skewed_info.value["skewed_column_names"]
          # skewed_column_value_location_maps - (optional) is a type of map of string
          skewed_column_value_location_maps = skewed_info.value["skewed_column_value_location_maps"]
          # skewed_column_values - (optional) is a type of list of string
          skewed_column_values = skewed_info.value["skewed_column_values"]
        }
      }

      dynamic "sort_columns" {
        for_each = storage_descriptor.value.sort_columns
        content {
          # column - (required) is a type of string
          column = sort_columns.value["column"]
          # sort_order - (required) is a type of number
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
output "catalog_id" {
  description = "returns a string"
  value       = aws_glue_partition.this.catalog_id
}

output "creation_time" {
  description = "returns a string"
  value       = aws_glue_partition.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = aws_glue_partition.this.id
}

output "last_accessed_time" {
  description = "returns a string"
  value       = aws_glue_partition.this.last_accessed_time
}

output "last_analyzed_time" {
  description = "returns a string"
  value       = aws_glue_partition.this.last_analyzed_time
}

output "this" {
  value = aws_glue_partition.this
}
```

[top](#index)