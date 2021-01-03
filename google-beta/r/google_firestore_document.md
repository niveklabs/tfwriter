# google_firestore_document

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_firestore_document" {
  source = "./modules/google-beta/r/google_firestore_document"

  # collection - (required) is a type of string
  collection = null
  # database - (optional) is a type of string
  database = null
  # document_id - (required) is a type of string
  document_id = null
  # fields - (required) is a type of string
  fields = null
  # project - (optional) is a type of string
  project = null

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
variable "collection" {
  description = "(required) - The collection ID, relative to database. For example: chatrooms or chatrooms/my-document/private-messages."
  type        = string
}

variable "database" {
  description = "(optional) - The Firestore database id. Defaults to '\"(default)\"'."
  type        = string
  default     = null
}

variable "document_id" {
  description = "(required) - The client-assigned document ID to use for this document during creation."
  type        = string
}

variable "fields" {
  description = "(required) - The document's [fields](https://cloud.google.com/firestore/docs/reference/rest/v1/projects.databases.documents) formated as a json string."
  type        = string
}

variable "project" {
  description = "(optional)"
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
resource "google_firestore_document" "this" {
  collection  = var.collection
  database    = var.database
  document_id = var.document_id
  fields      = var.fields
  project     = var.project

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
  value       = google_firestore_document.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_firestore_document.this.id
}

output "name" {
  description = "returns a string"
  value       = google_firestore_document.this.name
}

output "path" {
  description = "returns a string"
  value       = google_firestore_document.this.path
}

output "project" {
  description = "returns a string"
  value       = google_firestore_document.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_firestore_document.this.update_time
}

output "this" {
  value = google_firestore_document.this
}
```

[top](#index)