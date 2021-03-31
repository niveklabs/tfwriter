# google_bigquery_job

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigquery_job" {
  source = "./modules/google/r/google_bigquery_job"

  # job_id - (required) is a type of string
  job_id = null
  # job_timeout_ms - (optional) is a type of string
  job_timeout_ms = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null

  copy = [{
    create_disposition = null
    destination_encryption_configuration = [{
      kms_key_name = null
    }]
    destination_table = [{
      dataset_id = null
      project_id = null
      table_id   = null
    }]
    source_tables = [{
      dataset_id = null
      project_id = null
      table_id   = null
    }]
    write_disposition = null
  }]

  extract = [{
    compression        = null
    destination_format = null
    destination_uris   = []
    field_delimiter    = null
    print_header       = null
    source_model = [{
      dataset_id = null
      model_id   = null
      project_id = null
    }]
    source_table = [{
      dataset_id = null
      project_id = null
      table_id   = null
    }]
    use_avro_logical_types = null
  }]

  load = [{
    allow_jagged_rows     = null
    allow_quoted_newlines = null
    autodetect            = null
    create_disposition    = null
    destination_encryption_configuration = [{
      kms_key_name = null
    }]
    destination_table = [{
      dataset_id = null
      project_id = null
      table_id   = null
    }]
    encoding              = null
    field_delimiter       = null
    ignore_unknown_values = null
    max_bad_records       = null
    null_marker           = null
    projection_fields     = []
    quote                 = null
    schema_update_options = []
    skip_leading_rows     = null
    source_format         = null
    source_uris           = []
    time_partitioning = [{
      expiration_ms = null
      field         = null
      type          = null
    }]
    write_disposition = null
  }]

  query = [{
    allow_large_results = null
    create_disposition  = null
    default_dataset = [{
      dataset_id = null
      project_id = null
    }]
    destination_encryption_configuration = [{
      kms_key_name = null
    }]
    destination_table = [{
      dataset_id = null
      project_id = null
      table_id   = null
    }]
    flatten_results       = null
    maximum_billing_tier  = null
    maximum_bytes_billed  = null
    parameter_mode        = null
    priority              = null
    query                 = null
    schema_update_options = []
    script_options = [{
      key_result_statement  = null
      statement_byte_budget = null
      statement_timeout_ms  = null
    }]
    use_legacy_sql  = null
    use_query_cache = null
    user_defined_function_resources = [{
      inline_code  = null
      resource_uri = null
    }]
    write_disposition = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "job_id" {
  description = "(required) - The ID of the job. The ID must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), or dashes (-). The maximum length is 1,024 characters."
  type        = string
}

variable "job_timeout_ms" {
  description = "(optional) - Job timeout in milliseconds. If this time limit is exceeded, BigQuery may attempt to terminate the job."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The labels associated with this job. You can use these to organize and group your jobs."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - The geographic location of the job. The default value is US."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "copy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      create_disposition = string
      destination_encryption_configuration = list(object(
        {
          kms_key_name = string
        }
      ))
      destination_table = list(object(
        {
          dataset_id = string
          project_id = string
          table_id   = string
        }
      ))
      source_tables = list(object(
        {
          dataset_id = string
          project_id = string
          table_id   = string
        }
      ))
      write_disposition = string
    }
  ))
  default = []
}

variable "extract" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      compression        = string
      destination_format = string
      destination_uris   = list(string)
      field_delimiter    = string
      print_header       = bool
      source_model = list(object(
        {
          dataset_id = string
          model_id   = string
          project_id = string
        }
      ))
      source_table = list(object(
        {
          dataset_id = string
          project_id = string
          table_id   = string
        }
      ))
      use_avro_logical_types = bool
    }
  ))
  default = []
}

variable "load" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_jagged_rows     = bool
      allow_quoted_newlines = bool
      autodetect            = bool
      create_disposition    = string
      destination_encryption_configuration = list(object(
        {
          kms_key_name = string
        }
      ))
      destination_table = list(object(
        {
          dataset_id = string
          project_id = string
          table_id   = string
        }
      ))
      encoding              = string
      field_delimiter       = string
      ignore_unknown_values = bool
      max_bad_records       = number
      null_marker           = string
      projection_fields     = list(string)
      quote                 = string
      schema_update_options = list(string)
      skip_leading_rows     = number
      source_format         = string
      source_uris           = list(string)
      time_partitioning = list(object(
        {
          expiration_ms = string
          field         = string
          type          = string
        }
      ))
      write_disposition = string
    }
  ))
  default = []
}

variable "query" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_large_results = bool
      create_disposition  = string
      default_dataset = list(object(
        {
          dataset_id = string
          project_id = string
        }
      ))
      destination_encryption_configuration = list(object(
        {
          kms_key_name = string
        }
      ))
      destination_table = list(object(
        {
          dataset_id = string
          project_id = string
          table_id   = string
        }
      ))
      flatten_results       = bool
      maximum_billing_tier  = number
      maximum_bytes_billed  = string
      parameter_mode        = string
      priority              = string
      query                 = string
      schema_update_options = list(string)
      script_options = list(object(
        {
          key_result_statement  = string
          statement_byte_budget = string
          statement_timeout_ms  = string
        }
      ))
      use_legacy_sql  = bool
      use_query_cache = bool
      user_defined_function_resources = list(object(
        {
          inline_code  = string
          resource_uri = string
        }
      ))
      write_disposition = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_bigquery_job" "this" {
  job_id         = var.job_id
  job_timeout_ms = var.job_timeout_ms
  labels         = var.labels
  location       = var.location
  project        = var.project

  dynamic "copy" {
    for_each = var.copy
    content {
      create_disposition = copy.value["create_disposition"]
      write_disposition  = copy.value["write_disposition"]

      dynamic "destination_encryption_configuration" {
        for_each = copy.value.destination_encryption_configuration
        content {
          kms_key_name = destination_encryption_configuration.value["kms_key_name"]
        }
      }

      dynamic "destination_table" {
        for_each = copy.value.destination_table
        content {
          dataset_id = destination_table.value["dataset_id"]
          project_id = destination_table.value["project_id"]
          table_id   = destination_table.value["table_id"]
        }
      }

      dynamic "source_tables" {
        for_each = copy.value.source_tables
        content {
          dataset_id = source_tables.value["dataset_id"]
          project_id = source_tables.value["project_id"]
          table_id   = source_tables.value["table_id"]
        }
      }

    }
  }

  dynamic "extract" {
    for_each = var.extract
    content {
      compression            = extract.value["compression"]
      destination_format     = extract.value["destination_format"]
      destination_uris       = extract.value["destination_uris"]
      field_delimiter        = extract.value["field_delimiter"]
      print_header           = extract.value["print_header"]
      use_avro_logical_types = extract.value["use_avro_logical_types"]

      dynamic "source_model" {
        for_each = extract.value.source_model
        content {
          dataset_id = source_model.value["dataset_id"]
          model_id   = source_model.value["model_id"]
          project_id = source_model.value["project_id"]
        }
      }

      dynamic "source_table" {
        for_each = extract.value.source_table
        content {
          dataset_id = source_table.value["dataset_id"]
          project_id = source_table.value["project_id"]
          table_id   = source_table.value["table_id"]
        }
      }

    }
  }

  dynamic "load" {
    for_each = var.load
    content {
      allow_jagged_rows     = load.value["allow_jagged_rows"]
      allow_quoted_newlines = load.value["allow_quoted_newlines"]
      autodetect            = load.value["autodetect"]
      create_disposition    = load.value["create_disposition"]
      encoding              = load.value["encoding"]
      field_delimiter       = load.value["field_delimiter"]
      ignore_unknown_values = load.value["ignore_unknown_values"]
      max_bad_records       = load.value["max_bad_records"]
      null_marker           = load.value["null_marker"]
      projection_fields     = load.value["projection_fields"]
      quote                 = load.value["quote"]
      schema_update_options = load.value["schema_update_options"]
      skip_leading_rows     = load.value["skip_leading_rows"]
      source_format         = load.value["source_format"]
      source_uris           = load.value["source_uris"]
      write_disposition     = load.value["write_disposition"]

      dynamic "destination_encryption_configuration" {
        for_each = load.value.destination_encryption_configuration
        content {
          kms_key_name = destination_encryption_configuration.value["kms_key_name"]
        }
      }

      dynamic "destination_table" {
        for_each = load.value.destination_table
        content {
          dataset_id = destination_table.value["dataset_id"]
          project_id = destination_table.value["project_id"]
          table_id   = destination_table.value["table_id"]
        }
      }

      dynamic "time_partitioning" {
        for_each = load.value.time_partitioning
        content {
          expiration_ms = time_partitioning.value["expiration_ms"]
          field         = time_partitioning.value["field"]
          type          = time_partitioning.value["type"]
        }
      }

    }
  }

  dynamic "query" {
    for_each = var.query
    content {
      allow_large_results   = query.value["allow_large_results"]
      create_disposition    = query.value["create_disposition"]
      flatten_results       = query.value["flatten_results"]
      maximum_billing_tier  = query.value["maximum_billing_tier"]
      maximum_bytes_billed  = query.value["maximum_bytes_billed"]
      parameter_mode        = query.value["parameter_mode"]
      priority              = query.value["priority"]
      query                 = query.value["query"]
      schema_update_options = query.value["schema_update_options"]
      use_legacy_sql        = query.value["use_legacy_sql"]
      use_query_cache       = query.value["use_query_cache"]
      write_disposition     = query.value["write_disposition"]

      dynamic "default_dataset" {
        for_each = query.value.default_dataset
        content {
          dataset_id = default_dataset.value["dataset_id"]
          project_id = default_dataset.value["project_id"]
        }
      }

      dynamic "destination_encryption_configuration" {
        for_each = query.value.destination_encryption_configuration
        content {
          kms_key_name = destination_encryption_configuration.value["kms_key_name"]
        }
      }

      dynamic "destination_table" {
        for_each = query.value.destination_table
        content {
          dataset_id = destination_table.value["dataset_id"]
          project_id = destination_table.value["project_id"]
          table_id   = destination_table.value["table_id"]
        }
      }

      dynamic "script_options" {
        for_each = query.value.script_options
        content {
          key_result_statement  = script_options.value["key_result_statement"]
          statement_byte_budget = script_options.value["statement_byte_budget"]
          statement_timeout_ms  = script_options.value["statement_timeout_ms"]
        }
      }

      dynamic "user_defined_function_resources" {
        for_each = query.value.user_defined_function_resources
        content {
          inline_code  = user_defined_function_resources.value["inline_code"]
          resource_uri = user_defined_function_resources.value["resource_uri"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_bigquery_job.this.id
}

output "job_type" {
  description = "returns a string"
  value       = google_bigquery_job.this.job_type
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_job.this.project
}

output "status" {
  description = "returns a list of object"
  value       = google_bigquery_job.this.status
}

output "user_email" {
  description = "returns a string"
  value       = google_bigquery_job.this.user_email
}

output "this" {
  value = google_bigquery_job.this
}
```

[top](#index)