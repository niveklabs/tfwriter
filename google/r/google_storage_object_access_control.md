# google_storage_object_access_control

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_storage_object_access_control" {
  source = "./modules/google/r/google_storage_object_access_control"

  # bucket - (required) is a type of string
  bucket = null
  # entity - (required) is a type of string
  entity = null
  # object - (required) is a type of string
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

```hcl
variable "bucket" {
  description = "(required) - The name of the bucket."
  type        = string
}

variable "entity" {
  description = "(required) - The entity holding the permission, in one of the following forms:\n  * user-{{userId}}\n  * user-{{email}} (such as \"user-liz@example.com\")\n  * group-{{groupId}}\n  * group-{{email}} (such as \"group-example@googlegroups.com\")\n  * domain-{{domain}} (such as \"domain-example.com\")\n  * project-team-{{projectId}}\n  * allUsers\n  * allAuthenticatedUsers"
  type        = string
}

variable "object" {
  description = "(required) - The name of the object to apply the access control to."
  type        = string
}

variable "role" {
  description = "(required) - The access permission for the entity. Possible values: [\"OWNER\", \"READER\"]"
  type        = string
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
resource "google_storage_object_access_control" "this" {
  bucket = var.bucket
  entity = var.entity
  object = var.object
  role   = var.role

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
output "domain" {
  description = "returns a string"
  value       = google_storage_object_access_control.this.domain
}

output "email" {
  description = "returns a string"
  value       = google_storage_object_access_control.this.email
}

output "entity_id" {
  description = "returns a string"
  value       = google_storage_object_access_control.this.entity_id
}

output "generation" {
  description = "returns a number"
  value       = google_storage_object_access_control.this.generation
}

output "id" {
  description = "returns a string"
  value       = google_storage_object_access_control.this.id
}

output "project_team" {
  description = "returns a list of object"
  value       = google_storage_object_access_control.this.project_team
}

output "this" {
  value = google_storage_object_access_control.this
}
```

[top](#index)