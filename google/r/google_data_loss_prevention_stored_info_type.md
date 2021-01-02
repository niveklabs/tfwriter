# google_data_loss_prevention_stored_info_type

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
module "google_data_loss_prevention_stored_info_type" {
  source = "./modules/google/r/google_data_loss_prevention_stored_info_type"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # parent - (required) is a type of string
  parent = null

  dictionary = [{
    cloud_storage_path = [{
      path = null
    }]
    word_list = [{
      words = []
    }]
  }]

  large_custom_dictionary = [{
    big_query_field = [{
      field = [{
        name = null
      }]
      table = [{
        dataset_id = null
        project_id = null
        table_id   = null
      }]
    }]
    cloud_storage_file_set = [{
      url = null
    }]
    output_path = [{
      path = null
    }]
  }]

  regex = [{
    group_indexes = []
    pattern       = null
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
  description = "(optional) - A description of the info type."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - User set display name of the info type."
  type        = string
  default     = null
}

variable "parent" {
  description = "(required) - The parent of the info type in any of the following formats:\n\n* 'projects/{{project}}'\n* 'projects/{{project}}/locations/{{location}}'\n* 'organizations/{{organization_id}}'\n* 'organizations/{{organization_id}}/locations/{{location}}'"
  type        = string
}

variable "dictionary" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_storage_path = list(object(
        {
          path = string
        }
      ))
      word_list = list(object(
        {
          words = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "large_custom_dictionary" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      big_query_field = list(object(
        {
          field = list(object(
            {
              name = string
            }
          ))
          table = list(object(
            {
              dataset_id = string
              project_id = string
              table_id   = string
            }
          ))
        }
      ))
      cloud_storage_file_set = list(object(
        {
          url = string
        }
      ))
      output_path = list(object(
        {
          path = string
        }
      ))
    }
  ))
  default = []
}

variable "regex" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group_indexes = list(number)
      pattern       = string
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
resource "google_data_loss_prevention_stored_info_type" "this" {
  description  = var.description
  display_name = var.display_name
  parent       = var.parent

  dynamic "dictionary" {
    for_each = var.dictionary
    content {

      dynamic "cloud_storage_path" {
        for_each = dictionary.value.cloud_storage_path
        content {
          path = cloud_storage_path.value["path"]
        }
      }

      dynamic "word_list" {
        for_each = dictionary.value.word_list
        content {
          words = word_list.value["words"]
        }
      }

    }
  }

  dynamic "large_custom_dictionary" {
    for_each = var.large_custom_dictionary
    content {

      dynamic "big_query_field" {
        for_each = large_custom_dictionary.value.big_query_field
        content {

          dynamic "field" {
            for_each = big_query_field.value.field
            content {
              name = field.value["name"]
            }
          }

          dynamic "table" {
            for_each = big_query_field.value.table
            content {
              dataset_id = table.value["dataset_id"]
              project_id = table.value["project_id"]
              table_id   = table.value["table_id"]
            }
          }

        }
      }

      dynamic "cloud_storage_file_set" {
        for_each = large_custom_dictionary.value.cloud_storage_file_set
        content {
          url = cloud_storage_file_set.value["url"]
        }
      }

      dynamic "output_path" {
        for_each = large_custom_dictionary.value.output_path
        content {
          path = output_path.value["path"]
        }
      }

    }
  }

  dynamic "regex" {
    for_each = var.regex
    content {
      group_indexes = regex.value["group_indexes"]
      pattern       = regex.value["pattern"]
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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_data_loss_prevention_stored_info_type.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_loss_prevention_stored_info_type.this.name
}

output "this" {
  value = google_data_loss_prevention_stored_info_type.this
}
```

[top](#index)