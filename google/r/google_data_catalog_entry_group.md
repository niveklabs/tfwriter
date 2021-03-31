# google_data_catalog_entry_group

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
module "google_data_catalog_entry_group" {
  source = "./modules/google/r/google_data_catalog_entry_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # entry_group_id - (required) is a type of string
  entry_group_id = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

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
  description = "(optional) - Entry group description, which can consist of several sentences or paragraphs that describe entry group contents."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - A short name to identify the entry group, for example, \"analytics data - jan 2011\"."
  type        = string
  default     = null
}

variable "entry_group_id" {
  description = "(required) - The id of the entry group to create. The id must begin with a letter or underscore,\ncontain only English letters, numbers and underscores, and be at most 64 characters."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - EntryGroup location region."
  type        = string
  default     = null
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
resource "google_data_catalog_entry_group" "this" {
  description    = var.description
  display_name   = var.display_name
  entry_group_id = var.entry_group_id
  project        = var.project
  region         = var.region

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
  value       = google_data_catalog_entry_group.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_catalog_entry_group.this.name
}

output "project" {
  description = "returns a string"
  value       = google_data_catalog_entry_group.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_catalog_entry_group.this.region
}

output "this" {
  value = google_data_catalog_entry_group.this
}
```

[top](#index)