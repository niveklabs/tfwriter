# google_bigquery_table

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigquery_table" {
  source = "./modules/google/r/google_bigquery_table"

  # clustering - (optional) is a type of list of string
  clustering = []
  # dataset_id - (required) is a type of string
  dataset_id = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # description - (optional) is a type of string
  description = null
  # expiration_time - (optional) is a type of number
  expiration_time = null
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null
  # schema - (optional) is a type of string
  schema = null
  # table_id - (required) is a type of string
  table_id = null

  encryption_configuration = [{
    kms_key_name = null
  }]

  external_data_configuration = [{
    autodetect  = null
    compression = null
    csv_options = [{
      allow_jagged_rows     = null
      allow_quoted_newlines = null
      encoding              = null
      field_delimiter       = null
      quote                 = null
      skip_leading_rows     = null
    }]
    google_sheets_options = [{
      range             = null
      skip_leading_rows = null
    }]
    hive_partitioning_options = [{
      mode              = null
      source_uri_prefix = null
    }]
    ignore_unknown_values = null
    max_bad_records       = null
    schema                = null
    source_format         = null
    source_uris           = []
  }]

  materialized_view = [{
    enable_refresh      = null
    query               = null
    refresh_interval_ms = null
  }]

  range_partitioning = [{
    field = null
    range = [{
      end      = null
      interval = null
      start    = null
    }]
  }]

  time_partitioning = [{
    expiration_ms            = null
    field                    = null
    require_partition_filter = null
    type                     = null
  }]

  view = [{
    query          = null
    use_legacy_sql = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "clustering" {
  description = "(optional) - Specifies column names to use for data clustering. Up to four top-level columns are allowed, and should be specified in descending priority order."
  type        = list(string)
  default     = null
}

variable "dataset_id" {
  description = "(required) - The dataset ID to create the table in. Changing this forces a new resource to be created."
  type        = string
}

variable "deletion_protection" {
  description = "(optional) - Whether or not to allow Terraform to destroy the instance. Unless this field is set to false in Terraform state, a terraform destroy or terraform apply that would delete the instance will fail."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The field description."
  type        = string
  default     = null
}

variable "expiration_time" {
  description = "(optional) - The time when this table expires, in milliseconds since the epoch. If not present, the table will persist indefinitely. Expired tables will be deleted and their storage reclaimed."
  type        = number
  default     = null
}

variable "friendly_name" {
  description = "(optional) - A descriptive name for the table."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A mapping of labels to assign to the resource."
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs."
  type        = string
  default     = null
}

variable "schema" {
  description = "(optional) - A JSON schema for the table."
  type        = string
  default     = null
}

variable "table_id" {
  description = "(required) - A unique ID for the resource. Changing this forces a new resource to be created."
  type        = string
}

variable "encryption_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_key_name = string
    }
  ))
  default = []
}

variable "external_data_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      autodetect  = bool
      compression = string
      csv_options = list(object(
        {
          allow_jagged_rows     = bool
          allow_quoted_newlines = bool
          encoding              = string
          field_delimiter       = string
          quote                 = string
          skip_leading_rows     = number
        }
      ))
      google_sheets_options = list(object(
        {
          range             = string
          skip_leading_rows = number
        }
      ))
      hive_partitioning_options = list(object(
        {
          mode              = string
          source_uri_prefix = string
        }
      ))
      ignore_unknown_values = bool
      max_bad_records       = number
      schema                = string
      source_format         = string
      source_uris           = list(string)
    }
  ))
  default = []
}

variable "materialized_view" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_refresh      = bool
      query               = string
      refresh_interval_ms = number
    }
  ))
  default = []
}

variable "range_partitioning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      field = string
      range = list(object(
        {
          end      = number
          interval = number
          start    = number
        }
      ))
    }
  ))
  default = []
}

variable "time_partitioning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      expiration_ms            = number
      field                    = string
      require_partition_filter = bool
      type                     = string
    }
  ))
  default = []
}

variable "view" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      query          = string
      use_legacy_sql = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_bigquery_table" "this" {
  clustering          = var.clustering
  dataset_id          = var.dataset_id
  deletion_protection = var.deletion_protection
  description         = var.description
  expiration_time     = var.expiration_time
  friendly_name       = var.friendly_name
  labels              = var.labels
  project             = var.project
  schema              = var.schema
  table_id            = var.table_id

  dynamic "encryption_configuration" {
    for_each = var.encryption_configuration
    content {
      kms_key_name = encryption_configuration.value["kms_key_name"]
    }
  }

  dynamic "external_data_configuration" {
    for_each = var.external_data_configuration
    content {
      autodetect            = external_data_configuration.value["autodetect"]
      compression           = external_data_configuration.value["compression"]
      ignore_unknown_values = external_data_configuration.value["ignore_unknown_values"]
      max_bad_records       = external_data_configuration.value["max_bad_records"]
      schema                = external_data_configuration.value["schema"]
      source_format         = external_data_configuration.value["source_format"]
      source_uris           = external_data_configuration.value["source_uris"]

      dynamic "csv_options" {
        for_each = external_data_configuration.value.csv_options
        content {
          allow_jagged_rows     = csv_options.value["allow_jagged_rows"]
          allow_quoted_newlines = csv_options.value["allow_quoted_newlines"]
          encoding              = csv_options.value["encoding"]
          field_delimiter       = csv_options.value["field_delimiter"]
          quote                 = csv_options.value["quote"]
          skip_leading_rows     = csv_options.value["skip_leading_rows"]
        }
      }

      dynamic "google_sheets_options" {
        for_each = external_data_configuration.value.google_sheets_options
        content {
          range             = google_sheets_options.value["range"]
          skip_leading_rows = google_sheets_options.value["skip_leading_rows"]
        }
      }

      dynamic "hive_partitioning_options" {
        for_each = external_data_configuration.value.hive_partitioning_options
        content {
          mode              = hive_partitioning_options.value["mode"]
          source_uri_prefix = hive_partitioning_options.value["source_uri_prefix"]
        }
      }

    }
  }

  dynamic "materialized_view" {
    for_each = var.materialized_view
    content {
      enable_refresh      = materialized_view.value["enable_refresh"]
      query               = materialized_view.value["query"]
      refresh_interval_ms = materialized_view.value["refresh_interval_ms"]
    }
  }

  dynamic "range_partitioning" {
    for_each = var.range_partitioning
    content {
      field = range_partitioning.value["field"]

      dynamic "range" {
        for_each = range_partitioning.value.range
        content {
          end      = range.value["end"]
          interval = range.value["interval"]
          start    = range.value["start"]
        }
      }

    }
  }

  dynamic "time_partitioning" {
    for_each = var.time_partitioning
    content {
      expiration_ms            = time_partitioning.value["expiration_ms"]
      field                    = time_partitioning.value["field"]
      require_partition_filter = time_partitioning.value["require_partition_filter"]
      type                     = time_partitioning.value["type"]
    }
  }

  dynamic "view" {
    for_each = var.view
    content {
      query          = view.value["query"]
      use_legacy_sql = view.value["use_legacy_sql"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_time" {
  description = "returns a number"
  value       = google_bigquery_table.this.creation_time
}

output "etag" {
  description = "returns a string"
  value       = google_bigquery_table.this.etag
}

output "expiration_time" {
  description = "returns a number"
  value       = google_bigquery_table.this.expiration_time
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_table.this.id
}

output "last_modified_time" {
  description = "returns a number"
  value       = google_bigquery_table.this.last_modified_time
}

output "location" {
  description = "returns a string"
  value       = google_bigquery_table.this.location
}

output "num_bytes" {
  description = "returns a number"
  value       = google_bigquery_table.this.num_bytes
}

output "num_long_term_bytes" {
  description = "returns a number"
  value       = google_bigquery_table.this.num_long_term_bytes
}

output "num_rows" {
  description = "returns a number"
  value       = google_bigquery_table.this.num_rows
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_table.this.project
}

output "schema" {
  description = "returns a string"
  value       = google_bigquery_table.this.schema
}

output "self_link" {
  description = "returns a string"
  value       = google_bigquery_table.this.self_link
}

output "type" {
  description = "returns a string"
  value       = google_bigquery_table.this.type
}

output "this" {
  value = google_bigquery_table.this
}
```

[top](#index)