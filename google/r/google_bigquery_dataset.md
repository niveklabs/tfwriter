# google_bigquery_dataset

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
module "google_bigquery_dataset" {
  source = "./modules/google/r/google_bigquery_dataset"

  # dataset_id - (required) is a type of string
  dataset_id = null
  # default_partition_expiration_ms - (optional) is a type of number
  default_partition_expiration_ms = null
  # default_table_expiration_ms - (optional) is a type of number
  default_table_expiration_ms = null
  # delete_contents_on_destroy - (optional) is a type of bool
  delete_contents_on_destroy = null
  # description - (optional) is a type of string
  description = null
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null

  access = [{
    domain         = null
    group_by_email = null
    role           = null
    special_group  = null
    user_by_email  = null
    view = [{
      dataset_id = null
      project_id = null
      table_id   = null
    }]
  }]

  default_encryption_configuration = [{
    kms_key_name = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dataset_id" {
  description = "(required) - A unique ID for this dataset, without the project name. The ID\nmust contain only letters (a-z, A-Z), numbers (0-9), or\nunderscores (_). The maximum length is 1,024 characters."
  type        = string
}

variable "default_partition_expiration_ms" {
  description = "(optional) - The default partition expiration for all partitioned tables in\nthe dataset, in milliseconds.\n\n\nOnce this property is set, all newly-created partitioned tables in\nthe dataset will have an 'expirationMs' property in the 'timePartitioning'\nsettings set to this value, and changing the value will only\naffect new tables, not existing ones. The storage in a partition will\nhave an expiration time of its partition time plus this value.\nSetting this property overrides the use of 'defaultTableExpirationMs'\nfor partitioned tables: only one of 'defaultTableExpirationMs' and\n'defaultPartitionExpirationMs' will be used for any new partitioned\ntable. If you provide an explicit 'timePartitioning.expirationMs' when\ncreating or updating a partitioned table, that value takes precedence\nover the default partition expiration time indicated by this property."
  type        = number
  default     = null
}

variable "default_table_expiration_ms" {
  description = "(optional) - The default lifetime of all tables in the dataset, in milliseconds.\nThe minimum value is 3600000 milliseconds (one hour).\n\n\nOnce this property is set, all newly-created tables in the dataset\nwill have an 'expirationTime' property set to the creation time plus\nthe value in this property, and changing the value will only affect\nnew tables, not existing ones. When the 'expirationTime' for a given\ntable is reached, that table will be deleted automatically.\nIf a table's 'expirationTime' is modified or removed before the\ntable expires, or if you provide an explicit 'expirationTime' when\ncreating a table, that value takes precedence over the default\nexpiration time indicated by this property."
  type        = number
  default     = null
}

variable "delete_contents_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - A user-friendly description of the dataset"
  type        = string
  default     = null
}

variable "friendly_name" {
  description = "(optional) - A descriptive name for the dataset"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The labels associated with this dataset. You can use these to\norganize and group your datasets"
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - The geographic location where the dataset should reside.\nSee [official docs](https://cloud.google.com/bigquery/docs/dataset-locations).\n\n\nThere are two types of locations, regional or multi-regional. A regional\nlocation is a specific geographic place, such as Tokyo, and a multi-regional\nlocation is a large geographic area, such as the United States, that\ncontains at least two geographic places.\n\n\nThe default value is multi-regional location 'US'.\nChanging this forces a new resource to be created."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      domain         = string
      group_by_email = string
      role           = string
      special_group  = string
      user_by_email  = string
      view = list(object(
        {
          dataset_id = string
          project_id = string
          table_id   = string
        }
      ))
    }
  ))
  default = []
}

variable "default_encryption_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_key_name = string
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
```

[top](#index)

### Resource

```terraform
resource "google_bigquery_dataset" "this" {
  # dataset_id - (required) is a type of string
  dataset_id = var.dataset_id
  # default_partition_expiration_ms - (optional) is a type of number
  default_partition_expiration_ms = var.default_partition_expiration_ms
  # default_table_expiration_ms - (optional) is a type of number
  default_table_expiration_ms = var.default_table_expiration_ms
  # delete_contents_on_destroy - (optional) is a type of bool
  delete_contents_on_destroy = var.delete_contents_on_destroy
  # description - (optional) is a type of string
  description = var.description
  # friendly_name - (optional) is a type of string
  friendly_name = var.friendly_name
  # labels - (optional) is a type of map of string
  labels = var.labels
  # location - (optional) is a type of string
  location = var.location
  # project - (optional) is a type of string
  project = var.project

  dynamic "access" {
    for_each = var.access
    content {
      # domain - (optional) is a type of string
      domain = access.value["domain"]
      # group_by_email - (optional) is a type of string
      group_by_email = access.value["group_by_email"]
      # role - (optional) is a type of string
      role = access.value["role"]
      # special_group - (optional) is a type of string
      special_group = access.value["special_group"]
      # user_by_email - (optional) is a type of string
      user_by_email = access.value["user_by_email"]

      dynamic "view" {
        for_each = access.value.view
        content {
          # dataset_id - (required) is a type of string
          dataset_id = view.value["dataset_id"]
          # project_id - (required) is a type of string
          project_id = view.value["project_id"]
          # table_id - (required) is a type of string
          table_id = view.value["table_id"]
        }
      }

    }
  }

  dynamic "default_encryption_configuration" {
    for_each = var.default_encryption_configuration
    content {
      # kms_key_name - (required) is a type of string
      kms_key_name = default_encryption_configuration.value["kms_key_name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_time" {
  description = "returns a number"
  value       = google_bigquery_dataset.this.creation_time
}

output "etag" {
  description = "returns a string"
  value       = google_bigquery_dataset.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_dataset.this.id
}

output "last_modified_time" {
  description = "returns a number"
  value       = google_bigquery_dataset.this.last_modified_time
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_dataset.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_bigquery_dataset.this.self_link
}

output "this" {
  value = google_bigquery_dataset.this
}
```

[top](#index)