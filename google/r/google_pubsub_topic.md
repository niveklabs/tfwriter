# google_pubsub_topic

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
module "google_pubsub_topic" {
  source = "./modules/google/r/google_pubsub_topic"

  # kms_key_name - (optional) is a type of string
  kms_key_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  message_storage_policy = [{
    allowed_persistence_regions = []
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
variable "kms_key_name" {
  description = "(optional) - The resource name of the Cloud KMS CryptoKey to be used to protect access\nto messages published on this topic. Your project's PubSub service account\n('service-{{PROJECT_NUMBER}}@gcp-sa-pubsub.iam.gserviceaccount.com') must have\n'roles/cloudkms.cryptoKeyEncrypterDecrypter' to use this feature.\nThe expected format is 'projects/*/locations/*/keyRings/*/cryptoKeys/*'"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to this Topic."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the topic."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "message_storage_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_persistence_regions = list(string)
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
resource "google_pubsub_topic" "this" {
  kms_key_name = var.kms_key_name
  labels       = var.labels
  name         = var.name
  project      = var.project

  dynamic "message_storage_policy" {
    for_each = var.message_storage_policy
    content {
      allowed_persistence_regions = message_storage_policy.value["allowed_persistence_regions"]
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
  value       = google_pubsub_topic.this.id
}

output "project" {
  description = "returns a string"
  value       = google_pubsub_topic.this.project
}

output "this" {
  value = google_pubsub_topic.this
}
```

[top](#index)