# google_firestore_index

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
module "google_firestore_index" {
  source = "./modules/google/r/google_firestore_index"

  # collection - (required) is a type of string
  collection = null
  # database - (optional) is a type of string
  database = null
  # project - (optional) is a type of string
  project = null
  # query_scope - (optional) is a type of string
  query_scope = null

  fields = [{
    array_config = null
    field_path   = null
    order        = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "collection" {
  description = "(required) - The collection being indexed."
  type        = string
}

variable "database" {
  description = "(optional) - The Firestore database id. Defaults to '\"(default)\"'."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_scope" {
  description = "(optional) - The scope at which a query is run. Default value: \"COLLECTION\" Possible values: [\"COLLECTION\", \"COLLECTION_GROUP\"]"
  type        = string
  default     = null
}

variable "fields" {
  description = "nested block: NestingList, min items: 2, max items: 0"
  type = set(object(
    {
      array_config = string
      field_path   = string
      order        = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_firestore_index" "this" {
  # collection - (required) is a type of string
  collection = var.collection
  # database - (optional) is a type of string
  database = var.database
  # project - (optional) is a type of string
  project = var.project
  # query_scope - (optional) is a type of string
  query_scope = var.query_scope

  dynamic "fields" {
    for_each = var.fields
    content {
      # array_config - (optional) is a type of string
      array_config = fields.value["array_config"]
      # field_path - (optional) is a type of string
      field_path = fields.value["field_path"]
      # order - (optional) is a type of string
      order = fields.value["order"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_firestore_index.this.id
}

output "name" {
  description = "returns a string"
  value       = google_firestore_index.this.name
}

output "project" {
  description = "returns a string"
  value       = google_firestore_index.this.project
}

output "this" {
  value = google_firestore_index.this
}
```

[top](#index)