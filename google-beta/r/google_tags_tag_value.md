# google_tags_tag_value

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_tags_tag_value" {
  source = "./modules/google-beta/r/google_tags_tag_value"

  # description - (optional) is a type of string
  description = null
  # parent - (required) is a type of string
  parent = null
  # short_name - (required) is a type of string
  short_name = null

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
  description = "(optional) - User-assigned description of the TagValue. Must not exceed 256 characters."
  type        = string
  default     = null
}

variable "parent" {
  description = "(required) - Input only. The resource name of the new TagValue's parent. Must be of the form tagKeys/{tag_key_id}."
  type        = string
}

variable "short_name" {
  description = "(required) - Input only. User-assigned short name for TagValue. The short name should be unique for TagValues within the same parent TagKey.\n\nThe short name must be 63 characters or less, beginning and ending with an alphanumeric character ([a-z0-9A-Z]) with dashes (-), underscores (_), dots (.), and alphanumerics between."
  type        = string
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
resource "google_tags_tag_value" "this" {
  # description - (optional) is a type of string
  description = var.description
  # parent - (required) is a type of string
  parent = var.parent
  # short_name - (required) is a type of string
  short_name = var.short_name

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
output "create_time" {
  description = "returns a string"
  value       = google_tags_tag_value.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_tags_tag_value.this.id
}

output "name" {
  description = "returns a string"
  value       = google_tags_tag_value.this.name
}

output "namespaced_name" {
  description = "returns a string"
  value       = google_tags_tag_value.this.namespaced_name
}

output "update_time" {
  description = "returns a string"
  value       = google_tags_tag_value.this.update_time
}

output "this" {
  value = google_tags_tag_value.this
}
```

[top](#index)