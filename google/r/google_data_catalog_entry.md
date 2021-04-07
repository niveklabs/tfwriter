# google_data_catalog_entry

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
module "google_data_catalog_entry" {
  source = "./modules/google/r/google_data_catalog_entry"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # entry_group - (required) is a type of string
  entry_group = null
  # entry_id - (required) is a type of string
  entry_id = null
  # linked_resource - (optional) is a type of string
  linked_resource = null
  # schema - (optional) is a type of string
  schema = null
  # type - (optional) is a type of string
  type = null
  # user_specified_system - (optional) is a type of string
  user_specified_system = null
  # user_specified_type - (optional) is a type of string
  user_specified_type = null

  gcs_fileset_spec = [{
    file_patterns = []
    sample_gcs_file_specs = [{
      file_path  = null
      size_bytes = null
    }]
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
variable "description" {
  description = "(optional) - Entry description, which can consist of several sentences or paragraphs that describe entry contents."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display information such as title and description. A short name to identify the entry,\nfor example, \"Analytics Data - Jan 2011\"."
  type        = string
  default     = null
}

variable "entry_group" {
  description = "(required) - The name of the entry group this entry is in."
  type        = string
}

variable "entry_id" {
  description = "(required) - The id of the entry to create."
  type        = string
}

variable "linked_resource" {
  description = "(optional) - The resource this metadata entry refers to.\nFor Google Cloud Platform resources, linkedResource is the full name of the resource.\nFor example, the linkedResource for a table resource from BigQuery is:\n//bigquery.googleapis.com/projects/projectId/datasets/datasetId/tables/tableId\nOutput only when Entry is of type in the EntryType enum. For entries with userSpecifiedType,\nthis field is optional and defaults to an empty string."
  type        = string
  default     = null
}

variable "schema" {
  description = "(optional) - Schema of the entry (e.g. BigQuery, GoogleSQL, Avro schema), as a json string. An entry might not have any schema\nattached to it. See\nhttps://cloud.google.com/data-catalog/docs/reference/rest/v1/projects.locations.entryGroups.entries#schema\nfor what fields this schema can contain."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - The type of the entry. Only used for Entries with types in the EntryType enum.\nCurrently, only FILESET enum value is allowed. All other entries created through Data Catalog must use userSpecifiedType. Possible values: [\"FILESET\"]"
  type        = string
  default     = null
}

variable "user_specified_system" {
  description = "(optional) - This field indicates the entry's source system that Data Catalog does not integrate with.\nuserSpecifiedSystem strings must begin with a letter or underscore and can only contain letters, numbers,\nand underscores; are case insensitive; must be at least 1 character and at most 64 characters long."
  type        = string
  default     = null
}

variable "user_specified_type" {
  description = "(optional) - Entry type if it does not fit any of the input-allowed values listed in EntryType enum above.\nWhen creating an entry, users should check the enum values first, if nothing matches the entry\nto be created, then provide a custom value, for example \"my_special_type\".\nuserSpecifiedType strings must begin with a letter or underscore and can only contain letters,\nnumbers, and underscores; are case insensitive; must be at least 1 character and at most 64 characters long."
  type        = string
  default     = null
}

variable "gcs_fileset_spec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      file_patterns = list(string)
      sample_gcs_file_specs = list(object(
        {
          file_path  = string
          size_bytes = number
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
```

[top](#index)

### Resource

```terraform
resource "google_data_catalog_entry" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # entry_group - (required) is a type of string
  entry_group = var.entry_group
  # entry_id - (required) is a type of string
  entry_id = var.entry_id
  # linked_resource - (optional) is a type of string
  linked_resource = var.linked_resource
  # schema - (optional) is a type of string
  schema = var.schema
  # type - (optional) is a type of string
  type = var.type
  # user_specified_system - (optional) is a type of string
  user_specified_system = var.user_specified_system
  # user_specified_type - (optional) is a type of string
  user_specified_type = var.user_specified_type

  dynamic "gcs_fileset_spec" {
    for_each = var.gcs_fileset_spec
    content {
      # file_patterns - (required) is a type of list of string
      file_patterns = gcs_fileset_spec.value["file_patterns"]
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
output "bigquery_date_sharded_spec" {
  description = "returns a list of object"
  value       = google_data_catalog_entry.this.bigquery_date_sharded_spec
}

output "bigquery_table_spec" {
  description = "returns a list of object"
  value       = google_data_catalog_entry.this.bigquery_table_spec
}

output "id" {
  description = "returns a string"
  value       = google_data_catalog_entry.this.id
}

output "integrated_system" {
  description = "returns a string"
  value       = google_data_catalog_entry.this.integrated_system
}

output "linked_resource" {
  description = "returns a string"
  value       = google_data_catalog_entry.this.linked_resource
}

output "name" {
  description = "returns a string"
  value       = google_data_catalog_entry.this.name
}

output "this" {
  value = google_data_catalog_entry.this
}
```

[top](#index)