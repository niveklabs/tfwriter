# google_storage_bucket_access_control

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
module "google_storage_bucket_access_control" {
  source = "./modules/google/r/google_storage_bucket_access_control"

  # bucket - (required) is a type of string
  bucket = null
  # entity - (required) is a type of string
  entity = null
  # role - (optional) is a type of string
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
  description = "(required) - The entity holding the permission, in one of the following forms:\n  user-userId\n  user-email\n  group-groupId\n  group-email\n  domain-domain\n  project-team-projectId\n  allUsers\n  allAuthenticatedUsers\nExamples:\n  The user liz@example.com would be user-liz@example.com.\n  The group example@googlegroups.com would be\n  group-example@googlegroups.com.\n  To refer to all members of the Google Apps for Business domain\n  example.com, the entity would be domain-example.com."
  type        = string
}

variable "role" {
  description = "(optional) - The access permission for the entity. Possible values: [\"OWNER\", \"READER\", \"WRITER\"]"
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
resource "google_storage_bucket_access_control" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # entity - (required) is a type of string
  entity = var.entity
  # role - (optional) is a type of string
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
  value       = google_storage_bucket_access_control.this.domain
}

output "email" {
  description = "returns a string"
  value       = google_storage_bucket_access_control.this.email
}

output "id" {
  description = "returns a string"
  value       = google_storage_bucket_access_control.this.id
}

output "this" {
  value = google_storage_bucket_access_control.this
}
```

[top](#index)