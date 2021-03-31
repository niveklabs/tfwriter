# google_storage_transfer_job

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_storage_transfer_job" {
  source = "./modules/google-beta/r/google_storage_transfer_job"

  # description - (required) is a type of string
  description = null
  # project - (optional) is a type of string
  project = null
  # status - (optional) is a type of string
  status = null

  schedule = [{
    schedule_end_date = [{
      day   = null
      month = null
      year  = null
    }]
    schedule_start_date = [{
      day   = null
      month = null
      year  = null
    }]
    start_time_of_day = [{
      hours   = null
      minutes = null
      nanos   = null
      seconds = null
    }]
  }]

  transfer_spec = [{
    aws_s3_data_source = [{
      aws_access_key = [{
        access_key_id     = null
        secret_access_key = null
      }]
      bucket_name = null
    }]
    gcs_data_sink = [{
      bucket_name = null
    }]
    gcs_data_source = [{
      bucket_name = null
    }]
    http_data_source = [{
      list_url = null
    }]
    object_conditions = [{
      exclude_prefixes                         = []
      include_prefixes                         = []
      max_time_elapsed_since_last_modification = null
      min_time_elapsed_since_last_modification = null
    }]
    transfer_options = [{
      delete_objects_from_source_after_transfer  = null
      delete_objects_unique_in_sink              = null
      overwrite_objects_already_existing_in_sink = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - Unique description to identify the Transfer Job."
  type        = string
}

variable "project" {
  description = "(optional) - The project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - Status of the job. Default: ENABLED. NOTE: The effect of the new job status takes place during a subsequent job run. For example, if you change the job status from ENABLED to DISABLED, and an operation spawned by the transfer is running, the status change would not affect the current operation."
  type        = string
  default     = null
}

variable "schedule" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      schedule_end_date = list(object(
        {
          day   = number
          month = number
          year  = number
        }
      ))
      schedule_start_date = list(object(
        {
          day   = number
          month = number
          year  = number
        }
      ))
      start_time_of_day = list(object(
        {
          hours   = number
          minutes = number
          nanos   = number
          seconds = number
        }
      ))
    }
  ))
}

variable "transfer_spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      aws_s3_data_source = list(object(
        {
          aws_access_key = list(object(
            {
              access_key_id     = string
              secret_access_key = string
            }
          ))
          bucket_name = string
        }
      ))
      gcs_data_sink = list(object(
        {
          bucket_name = string
        }
      ))
      gcs_data_source = list(object(
        {
          bucket_name = string
        }
      ))
      http_data_source = list(object(
        {
          list_url = string
        }
      ))
      object_conditions = list(object(
        {
          exclude_prefixes                         = list(string)
          include_prefixes                         = list(string)
          max_time_elapsed_since_last_modification = string
          min_time_elapsed_since_last_modification = string
        }
      ))
      transfer_options = list(object(
        {
          delete_objects_from_source_after_transfer  = bool
          delete_objects_unique_in_sink              = bool
          overwrite_objects_already_existing_in_sink = bool
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "google_storage_transfer_job" "this" {
  description = var.description
  project     = var.project
  status      = var.status

  dynamic "schedule" {
    for_each = var.schedule
    content {

      dynamic "schedule_end_date" {
        for_each = schedule.value.schedule_end_date
        content {
          day   = schedule_end_date.value["day"]
          month = schedule_end_date.value["month"]
          year  = schedule_end_date.value["year"]
        }
      }

      dynamic "schedule_start_date" {
        for_each = schedule.value.schedule_start_date
        content {
          day   = schedule_start_date.value["day"]
          month = schedule_start_date.value["month"]
          year  = schedule_start_date.value["year"]
        }
      }

      dynamic "start_time_of_day" {
        for_each = schedule.value.start_time_of_day
        content {
          hours   = start_time_of_day.value["hours"]
          minutes = start_time_of_day.value["minutes"]
          nanos   = start_time_of_day.value["nanos"]
          seconds = start_time_of_day.value["seconds"]
        }
      }

    }
  }

  dynamic "transfer_spec" {
    for_each = var.transfer_spec
    content {

      dynamic "aws_s3_data_source" {
        for_each = transfer_spec.value.aws_s3_data_source
        content {
          bucket_name = aws_s3_data_source.value["bucket_name"]

          dynamic "aws_access_key" {
            for_each = aws_s3_data_source.value.aws_access_key
            content {
              access_key_id     = aws_access_key.value["access_key_id"]
              secret_access_key = aws_access_key.value["secret_access_key"]
            }
          }

        }
      }

      dynamic "gcs_data_sink" {
        for_each = transfer_spec.value.gcs_data_sink
        content {
          bucket_name = gcs_data_sink.value["bucket_name"]
        }
      }

      dynamic "gcs_data_source" {
        for_each = transfer_spec.value.gcs_data_source
        content {
          bucket_name = gcs_data_source.value["bucket_name"]
        }
      }

      dynamic "http_data_source" {
        for_each = transfer_spec.value.http_data_source
        content {
          list_url = http_data_source.value["list_url"]
        }
      }

      dynamic "object_conditions" {
        for_each = transfer_spec.value.object_conditions
        content {
          exclude_prefixes                         = object_conditions.value["exclude_prefixes"]
          include_prefixes                         = object_conditions.value["include_prefixes"]
          max_time_elapsed_since_last_modification = object_conditions.value["max_time_elapsed_since_last_modification"]
          min_time_elapsed_since_last_modification = object_conditions.value["min_time_elapsed_since_last_modification"]
        }
      }

      dynamic "transfer_options" {
        for_each = transfer_spec.value.transfer_options
        content {
          delete_objects_from_source_after_transfer  = transfer_options.value["delete_objects_from_source_after_transfer"]
          delete_objects_unique_in_sink              = transfer_options.value["delete_objects_unique_in_sink"]
          overwrite_objects_already_existing_in_sink = transfer_options.value["overwrite_objects_already_existing_in_sink"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_time" {
  description = "returns a string"
  value       = google_storage_transfer_job.this.creation_time
}

output "deletion_time" {
  description = "returns a string"
  value       = google_storage_transfer_job.this.deletion_time
}

output "id" {
  description = "returns a string"
  value       = google_storage_transfer_job.this.id
}

output "last_modification_time" {
  description = "returns a string"
  value       = google_storage_transfer_job.this.last_modification_time
}

output "name" {
  description = "returns a string"
  value       = google_storage_transfer_job.this.name
}

output "project" {
  description = "returns a string"
  value       = google_storage_transfer_job.this.project
}

output "this" {
  value = google_storage_transfer_job.this
}
```

[top](#index)