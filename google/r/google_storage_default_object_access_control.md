# google_storage_default_object_access_control

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
module "google_storage_default_object_access_control" {
  source = "./modules/google/r/google_storage_default_object_access_control"

  # bucket - (required) is a type of string
  bucket = null
  # entity - (required) is a type of string
  entity = null
  # object - (optional) is a type of string
  object = null
  # role - (required) is a type of string
  role = null

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
variable "bucket" {
  description = "(required) - The name of the bucket."
  type        = string
}

variable "entity" {
  description = "(required) - The entity holding the permission, in one of the following forms:\n  * user-{{userId}}\n  * user-{{email}} (such as \"user-liz@example.com\")\n  * group-{{groupId}}\n  * group-{{email}} (such as \"group-example@googlegroups.com\")\n  * domain-{{domain}} (such as \"domain-example.com\")\n  * project-team-{{projectId}}\n  * allUsers\n  * allAuthenticatedUsers"
  type        = string
}

variable "object" {
  description = "(optional) - The name of the object, if applied to an object."
  type        = string
  default     = null
}

variable "role" {
  description = "(required) - The access permission for the entity. Possible values: [\"OWNER\", \"READER\"]"
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
resource "google_storage_default_object_access_control" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # entity - (required) is a type of string
  entity = var.entity
  # object - (optional) is a type of string
  object = var.object
  # role - (required) is a type of string
  role = var.role

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
output "domain" {
  description = "returns a string"
  value       = google_storage_default_object_access_control.this.domain
}

output "email" {
  description = "returns a string"
  value       = google_storage_default_object_access_control.this.email
}

output "entity_id" {
  description = "returns a string"
  value       = google_storage_default_object_access_control.this.entity_id
}

output "generation" {
  description = "returns a number"
  value       = google_storage_default_object_access_control.this.generation
}

output "id" {
  description = "returns a string"
  value       = google_storage_default_object_access_control.this.id
}

output "project_team" {
  description = "returns a list of object"
  value       = google_storage_default_object_access_control.this.project_team
}

output "this" {
  value = google_storage_default_object_access_control.this
}
```

[top](#index)