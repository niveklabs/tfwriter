# google_data_catalog_tag_template

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
module "google_data_catalog_tag_template" {
  source = "./modules/google/r/google_data_catalog_tag_template"

  # display_name - (optional) is a type of string
  display_name = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # tag_template_id - (required) is a type of string
  tag_template_id = null

  fields = [{
    display_name = null
    field_id     = null
    is_required  = null
    name         = null
    order        = null
    type = [{
      enum_type = [{
        allowed_values = [{
          display_name = null
        }]
      }]
      primitive_type = null
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

```hcl
variable "display_name" {
  description = "(optional) - The display name for this template."
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional) - This confirms the deletion of any possible tags using this template. Must be set to true in order to delete the tag template."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Template location region."
  type        = string
  default     = null
}

variable "tag_template_id" {
  description = "(required) - The id of the tag template to create."
  type        = string
}

variable "fields" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      display_name = string
      field_id     = string
      is_required  = bool
      name         = string
      order        = number
      type = list(object(
        {
          enum_type = list(object(
            {
              allowed_values = set(object(
                {
                  display_name = string
                }
              ))
            }
          ))
          primitive_type = string
        }
      ))
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
resource "google_data_catalog_tag_template" "this" {
  display_name    = var.display_name
  force_delete    = var.force_delete
  project         = var.project
  region          = var.region
  tag_template_id = var.tag_template_id

  dynamic "fields" {
    for_each = var.fields
    content {
      display_name = fields.value["display_name"]
      field_id     = fields.value["field_id"]
      is_required  = fields.value["is_required"]
      order        = fields.value["order"]

      dynamic "type" {
        for_each = fields.value.type
        content {
          primitive_type = type.value["primitive_type"]

          dynamic "enum_type" {
            for_each = type.value.enum_type
            content {

              dynamic "allowed_values" {
                for_each = enum_type.value.allowed_values
                content {
                  display_name = allowed_values.value["display_name"]
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

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_data_catalog_tag_template.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_catalog_tag_template.this.name
}

output "project" {
  description = "returns a string"
  value       = google_data_catalog_tag_template.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_catalog_tag_template.this.region
}

output "this" {
  value = google_data_catalog_tag_template.this
}
```

[top](#index)