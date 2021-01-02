# google_data_loss_prevention_job_trigger

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_data_loss_prevention_job_trigger" {
  source = "./modules/google/r/google_data_loss_prevention_job_trigger"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # parent - (required) is a type of string
  parent = null
  # status - (optional) is a type of string
  status = null

  inspect_job = [{
    actions = [{
      save_findings = [{
        output_config = [{
          output_schema = null
          table = [{
            dataset_id = null
            project_id = null
            table_id   = null
          }]
        }]
      }]
    }]
    inspect_template_name = null
    storage_config = [{
      big_query_options = [{
        table_reference = [{
          dataset_id = null
          project_id = null
          table_id   = null
        }]
      }]
      cloud_storage_options = [{
        bytes_limit_per_file         = null
        bytes_limit_per_file_percent = null
        file_set = [{
          regex_file_set = [{
            bucket_name   = null
            exclude_regex = []
            include_regex = []
          }]
          url = null
        }]
        file_types          = []
        files_limit_percent = null
        sample_method       = null
      }]
      datastore_options = [{
        kind = [{
          name = null
        }]
        partition_id = [{
          namespace_id = null
          project_id   = null
        }]
      }]
      timespan_config = [{
        enable_auto_population_of_timespan_config = null
        end_time                                  = null
        start_time                                = null
        timestamp_field = [{
          name = null
        }]
      }]
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  triggers = [{
    schedule = [{
      recurrence_period_duration = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A description of the job trigger."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - User set display name of the job trigger."
  type        = string
  default     = null
}

variable "parent" {
  description = "(required) - The parent of the trigger, either in the format 'projects/{{project}}'\nor 'projects/{{project}}/locations/{{location}}'"
  type        = string
}

variable "status" {
  description = "(optional) - Whether the trigger is currently active. Default value: \"HEALTHY\" Possible values: [\"PAUSED\", \"HEALTHY\", \"CANCELLED\"]"
  type        = string
  default     = null
}

variable "inspect_job" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      actions = list(object(
        {
          save_findings = list(object(
            {
              output_config = list(object(
                {
                  output_schema = string
                  table = list(object(
                    {
                      dataset_id = string
                      project_id = string
                      table_id   = string
                    }
                  ))
                }
              ))
            }
          ))
        }
      ))
      inspect_template_name = string
      storage_config = list(object(
        {
          big_query_options = list(object(
            {
              table_reference = list(object(
                {
                  dataset_id = string
                  project_id = string
                  table_id   = string
                }
              ))
            }
          ))
          cloud_storage_options = list(object(
            {
              bytes_limit_per_file         = number
              bytes_limit_per_file_percent = number
              file_set = list(object(
                {
                  regex_file_set = list(object(
                    {
                      bucket_name   = string
                      exclude_regex = list(string)
                      include_regex = list(string)
                    }
                  ))
                  url = string
                }
              ))
              file_types          = list(string)
              files_limit_percent = number
              sample_method       = string
            }
          ))
          datastore_options = list(object(
            {
              kind = list(object(
                {
                  name = string
                }
              ))
              partition_id = list(object(
                {
                  namespace_id = string
                  project_id   = string
                }
              ))
            }
          ))
          timespan_config = list(object(
            {
              enable_auto_population_of_timespan_config = bool
              end_time                                  = string
              start_time                                = string
              timestamp_field = list(object(
                {
                  name = string
                }
              ))
            }
          ))
        }
      ))
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
      update = string
    }
  ))
  default = []
}

variable "triggers" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      schedule = list(object(
        {
          recurrence_period_duration = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "google_data_loss_prevention_job_trigger" "this" {
  description  = var.description
  display_name = var.display_name
  parent       = var.parent
  status       = var.status

  dynamic "inspect_job" {
    for_each = var.inspect_job
    content {
      inspect_template_name = inspect_job.value["inspect_template_name"]

      dynamic "actions" {
        for_each = inspect_job.value.actions
        content {

          dynamic "save_findings" {
            for_each = actions.value.save_findings
            content {

              dynamic "output_config" {
                for_each = save_findings.value.output_config
                content {
                  output_schema = output_config.value["output_schema"]

                  dynamic "table" {
                    for_each = output_config.value.table
                    content {
                      dataset_id = table.value["dataset_id"]
                      project_id = table.value["project_id"]
                      table_id   = table.value["table_id"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "storage_config" {
        for_each = inspect_job.value.storage_config
        content {

          dynamic "big_query_options" {
            for_each = storage_config.value.big_query_options
            content {

              dynamic "table_reference" {
                for_each = big_query_options.value.table_reference
                content {
                  dataset_id = table_reference.value["dataset_id"]
                  project_id = table_reference.value["project_id"]
                  table_id   = table_reference.value["table_id"]
                }
              }

            }
          }

          dynamic "cloud_storage_options" {
            for_each = storage_config.value.cloud_storage_options
            content {
              bytes_limit_per_file         = cloud_storage_options.value["bytes_limit_per_file"]
              bytes_limit_per_file_percent = cloud_storage_options.value["bytes_limit_per_file_percent"]
              file_types                   = cloud_storage_options.value["file_types"]
              files_limit_percent          = cloud_storage_options.value["files_limit_percent"]
              sample_method                = cloud_storage_options.value["sample_method"]

              dynamic "file_set" {
                for_each = cloud_storage_options.value.file_set
                content {
                  url = file_set.value["url"]

                  dynamic "regex_file_set" {
                    for_each = file_set.value.regex_file_set
                    content {
                      bucket_name   = regex_file_set.value["bucket_name"]
                      exclude_regex = regex_file_set.value["exclude_regex"]
                      include_regex = regex_file_set.value["include_regex"]
                    }
                  }

                }
              }

            }
          }

          dynamic "datastore_options" {
            for_each = storage_config.value.datastore_options
            content {

              dynamic "kind" {
                for_each = datastore_options.value.kind
                content {
                  name = kind.value["name"]
                }
              }

              dynamic "partition_id" {
                for_each = datastore_options.value.partition_id
                content {
                  namespace_id = partition_id.value["namespace_id"]
                  project_id   = partition_id.value["project_id"]
                }
              }

            }
          }

          dynamic "timespan_config" {
            for_each = storage_config.value.timespan_config
            content {
              enable_auto_population_of_timespan_config = timespan_config.value["enable_auto_population_of_timespan_config"]
              end_time                                  = timespan_config.value["end_time"]
              start_time                                = timespan_config.value["start_time"]

              dynamic "timestamp_field" {
                for_each = timespan_config.value.timestamp_field
                content {
                  name = timestamp_field.value["name"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "triggers" {
    for_each = var.triggers
    content {

      dynamic "schedule" {
        for_each = triggers.value.schedule
        content {
          recurrence_period_duration = schedule.value["recurrence_period_duration"]
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
  value       = google_data_loss_prevention_job_trigger.this.id
}

output "last_run_time" {
  description = "returns a string"
  value       = google_data_loss_prevention_job_trigger.this.last_run_time
}

output "name" {
  description = "returns a string"
  value       = google_data_loss_prevention_job_trigger.this.name
}

output "this" {
  value = google_data_loss_prevention_job_trigger.this
}
```

[top](#index)