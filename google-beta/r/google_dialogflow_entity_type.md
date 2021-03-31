# google_dialogflow_entity_type

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
module "google_dialogflow_entity_type" {
  source = "./modules/google-beta/r/google_dialogflow_entity_type"

  # display_name - (required) is a type of string
  display_name = null
  # enable_fuzzy_extraction - (optional) is a type of bool
  enable_fuzzy_extraction = null
  # kind - (required) is a type of string
  kind = null
  # project - (optional) is a type of string
  project = null

  entities = [{
    synonyms = []
    value    = null
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

```terraform
variable "display_name" {
  description = "(required) - The name of this entity type to be displayed on the console."
  type        = string
}

variable "enable_fuzzy_extraction" {
  description = "(optional) - Enables fuzzy entity extraction during classification."
  type        = bool
  default     = null
}

variable "kind" {
  description = "(required) - Indicates the kind of entity type.\n* KIND_MAP: Map entity types allow mapping of a group of synonyms to a reference value.\n* KIND_LIST: List entity types contain a set of entries that do not map to reference values. However, list entity\ntypes can contain references to other entity types (with or without aliases).\n* KIND_REGEXP: Regexp entity types allow to specify regular expressions in entries values. Possible values: [\"KIND_MAP\", \"KIND_LIST\", \"KIND_REGEXP\"]"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entities" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      synonyms = list(string)
      value    = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_dialogflow_entity_type" "this" {
  display_name            = var.display_name
  enable_fuzzy_extraction = var.enable_fuzzy_extraction
  kind                    = var.kind
  project                 = var.project

  dynamic "entities" {
    for_each = var.entities
    content {
      synonyms = entities.value["synonyms"]
      value    = entities.value["value"]
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

```terraform
output "id" {
  description = "returns a string"
  value       = google_dialogflow_entity_type.this.id
}

output "name" {
  description = "returns a string"
  value       = google_dialogflow_entity_type.this.name
}

output "project" {
  description = "returns a string"
  value       = google_dialogflow_entity_type.this.project
}

output "this" {
  value = google_dialogflow_entity_type.this
}
```

[top](#index)