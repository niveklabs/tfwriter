# google_container_analysis_occurrence

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
module "google_container_analysis_occurrence" {
  source = "./modules/google/r/google_container_analysis_occurrence"

  # note_name - (required) is a type of string
  note_name = null
  # project - (optional) is a type of string
  project = null
  # remediation - (optional) is a type of string
  remediation = null
  # resource_uri - (required) is a type of string
  resource_uri = null

  attestation = [{
    serialized_payload = null
    signatures = [{
      public_key_id = null
      signature     = null
    }]
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
variable "note_name" {
  description = "(required) - The analysis note associated with this occurrence, in the form of\nprojects/[PROJECT]/notes/[NOTE_ID]. This field can be used as a\nfilter in list requests."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remediation" {
  description = "(optional) - A description of actions that can be taken to remedy the note."
  type        = string
  default     = null
}

variable "resource_uri" {
  description = "(required) - Required. Immutable. A URI that represents the resource for which\nthe occurrence applies. For example,\nhttps://gcr.io/project/image@sha256:123abc for a Docker image."
  type        = string
}

variable "attestation" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      serialized_payload = string
      signatures = set(object(
        {
          public_key_id = string
          signature     = string
        }
      ))
    }
  ))
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
resource "google_container_analysis_occurrence" "this" {
  note_name    = var.note_name
  project      = var.project
  remediation  = var.remediation
  resource_uri = var.resource_uri

  dynamic "attestation" {
    for_each = var.attestation
    content {
      serialized_payload = attestation.value["serialized_payload"]

      dynamic "signatures" {
        for_each = attestation.value.signatures
        content {
          public_key_id = signatures.value["public_key_id"]
          signature     = signatures.value["signature"]
        }
      }

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
output "create_time" {
  description = "returns a string"
  value       = google_container_analysis_occurrence.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_container_analysis_occurrence.this.id
}

output "kind" {
  description = "returns a string"
  value       = google_container_analysis_occurrence.this.kind
}

output "name" {
  description = "returns a string"
  value       = google_container_analysis_occurrence.this.name
}

output "project" {
  description = "returns a string"
  value       = google_container_analysis_occurrence.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_container_analysis_occurrence.this.update_time
}

output "this" {
  value = google_container_analysis_occurrence.this
}
```

[top](#index)