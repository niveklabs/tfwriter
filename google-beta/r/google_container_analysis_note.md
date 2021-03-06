# google_container_analysis_note

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
module "google_container_analysis_note" {
  source = "./modules/google-beta/r/google_container_analysis_note"

  # expiration_time - (optional) is a type of string
  expiration_time = null
  # long_description - (optional) is a type of string
  long_description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # related_note_names - (optional) is a type of set of string
  related_note_names = []
  # short_description - (optional) is a type of string
  short_description = null

  attestation_authority = [{
    hint = [{
      human_readable_name = null
    }]
  }]

  related_url = [{
    label = null
    url   = null
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
variable "expiration_time" {
  description = "(optional) - Time of expiration for this note. Leave empty if note does not expire."
  type        = string
  default     = null
}

variable "long_description" {
  description = "(optional) - A detailed description of the note"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the note."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "related_note_names" {
  description = "(optional) - Names of other notes related to this note."
  type        = set(string)
  default     = null
}

variable "short_description" {
  description = "(optional) - A one sentence description of the note."
  type        = string
  default     = null
}

variable "attestation_authority" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      hint = list(object(
        {
          human_readable_name = string
        }
      ))
    }
  ))
}

variable "related_url" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      label = string
      url   = string
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
resource "google_container_analysis_note" "this" {
  # expiration_time - (optional) is a type of string
  expiration_time = var.expiration_time
  # long_description - (optional) is a type of string
  long_description = var.long_description
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # related_note_names - (optional) is a type of set of string
  related_note_names = var.related_note_names
  # short_description - (optional) is a type of string
  short_description = var.short_description

  dynamic "attestation_authority" {
    for_each = var.attestation_authority
    content {

      dynamic "hint" {
        for_each = attestation_authority.value.hint
        content {
          # human_readable_name - (required) is a type of string
          human_readable_name = hint.value["human_readable_name"]
        }
      }

    }
  }

  dynamic "related_url" {
    for_each = var.related_url
    content {
      # label - (optional) is a type of string
      label = related_url.value["label"]
      # url - (required) is a type of string
      url = related_url.value["url"]
    }
  }

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
  value       = google_container_analysis_note.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_container_analysis_note.this.id
}

output "kind" {
  description = "returns a string"
  value       = google_container_analysis_note.this.kind
}

output "project" {
  description = "returns a string"
  value       = google_container_analysis_note.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_container_analysis_note.this.update_time
}

output "this" {
  value = google_container_analysis_note.this
}
```

[top](#index)