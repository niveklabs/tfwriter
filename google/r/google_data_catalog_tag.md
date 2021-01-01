# google_data_catalog_tag

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_data_catalog_tag" {
  source = "./modules/google/r/google_data_catalog_tag"

  # column - (optional) is a type of string
  column = null
  # parent - (optional) is a type of string
  parent = null
  # template - (required) is a type of string
  template = null

  fields = [{
    bool_value      = null
    display_name    = null
    double_value    = null
    enum_value      = null
    field_name      = null
    order           = null
    string_value    = null
    timestamp_value = null
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

```hcl
variable "column" {
  description = "(optional) - Resources like Entry can have schemas associated with them. This scope allows users to attach tags to an\nindividual column based on that schema.\n\nFor attaching a tag to a nested column, use '.' to separate the column names. Example:\n'outer_column.inner_column'"
  type        = string
  default     = null
}

variable "parent" {
  description = "(optional) - The name of the parent this tag is attached to. This can be the name of an entry or an entry group. If an entry group, the tag will be attached to\nall entries in that group."
  type        = string
  default     = null
}

variable "template" {
  description = "(required) - The resource name of the tag template that this tag uses. Example:\nprojects/{project_id}/locations/{location}/tagTemplates/{tagTemplateId}\nThis field cannot be modified after creation."
  type        = string
}

variable "fields" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      bool_value      = bool
      display_name    = string
      double_value    = number
      enum_value      = string
      field_name      = string
      order           = number
      string_value    = string
      timestamp_value = string
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_data_catalog_tag" "this" {
  column   = var.column
  parent   = var.parent
  template = var.template

  dynamic "fields" {
    for_each = var.fields
    content {
      bool_value      = fields.value["bool_value"]
      double_value    = fields.value["double_value"]
      enum_value      = fields.value["enum_value"]
      field_name      = fields.value["field_name"]
      string_value    = fields.value["string_value"]
      timestamp_value = fields.value["timestamp_value"]
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

```hcl
output "id" {
  description = "returns a string"
  value       = google_data_catalog_tag.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_catalog_tag.this.name
}

output "template_displayname" {
  description = "returns a string"
  value       = google_data_catalog_tag.this.template_displayname
}

output "this" {
  value = google_data_catalog_tag.this
}
```

[top](#index)