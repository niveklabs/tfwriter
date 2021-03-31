# google_tags_tag_key

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
module "google_tags_tag_key" {
  source = "./modules/google-beta/r/google_tags_tag_key"

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
  description = "(optional) - User-assigned description of the TagKey. Must not exceed 256 characters."
  type        = string
  default     = null
}

variable "parent" {
  description = "(required) - Input only. The resource name of the new TagKey's parent. Must be of the form organizations/{org_id}."
  type        = string
}

variable "short_name" {
  description = "(required) - Input only. The user friendly name for a TagKey. The short name should be unique for TagKeys within the same tag namespace.\n\nThe short name must be 1-63 characters, beginning and ending with an alphanumeric character ([a-z0-9A-Z]) with dashes (-), underscores (_), dots (.), and alphanumerics between."
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
resource "google_tags_tag_key" "this" {
  description = var.description
  parent      = var.parent
  short_name  = var.short_name

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
output "create_time" {
  description = "returns a string"
  value       = google_tags_tag_key.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_tags_tag_key.this.id
}

output "name" {
  description = "returns a string"
  value       = google_tags_tag_key.this.name
}

output "namespaced_name" {
  description = "returns a string"
  value       = google_tags_tag_key.this.namespaced_name
}

output "update_time" {
  description = "returns a string"
  value       = google_tags_tag_key.this.update_time
}

output "this" {
  value = google_tags_tag_key.this
}
```

[top](#index)