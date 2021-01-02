# google_datastore_index

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_datastore_index" {
  source = "./modules/google/r/google_datastore_index"

  # ancestor - (optional) is a type of string
  ancestor = null
  # kind - (required) is a type of string
  kind = null
  # project - (optional) is a type of string
  project = null

  properties = [{
    direction = null
    name      = null
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
variable "ancestor" {
  description = "(optional) - Policy for including ancestors in the index. Default value: \"NONE\" Possible values: [\"NONE\", \"ALL_ANCESTORS\"]"
  type        = string
  default     = null
}

variable "kind" {
  description = "(required) - The entity kind which the index applies to."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "properties" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      direction = string
      name      = string
    }
  ))
  default = []
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
resource "google_datastore_index" "this" {
  ancestor = var.ancestor
  kind     = var.kind
  project  = var.project

  dynamic "properties" {
    for_each = var.properties
    content {
      direction = properties.value["direction"]
      name      = properties.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
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
  value       = google_datastore_index.this.id
}

output "index_id" {
  description = "returns a string"
  value       = google_datastore_index.this.index_id
}

output "project" {
  description = "returns a string"
  value       = google_datastore_index.this.project
}

output "this" {
  value = google_datastore_index.this
}
```

[top](#index)