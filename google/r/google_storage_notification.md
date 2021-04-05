# google_storage_notification

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
module "google_storage_notification" {
  source = "./modules/google/r/google_storage_notification"

  # bucket - (required) is a type of string
  bucket = null
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # event_types - (optional) is a type of set of string
  event_types = []
  # object_name_prefix - (optional) is a type of string
  object_name_prefix = null
  # payload_format - (required) is a type of string
  payload_format = null
  # topic - (required) is a type of string
  topic = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required) - The name of the bucket."
  type        = string
}

variable "custom_attributes" {
  description = "(optional) -  A set of key/value attribute pairs to attach to each Cloud Pub/Sub message published for this notification subscription"
  type        = map(string)
  default     = null
}

variable "event_types" {
  description = "(optional) - List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: \"OBJECT_FINALIZE\", \"OBJECT_METADATA_UPDATE\", \"OBJECT_DELETE\", \"OBJECT_ARCHIVE\""
  type        = set(string)
  default     = null
}

variable "object_name_prefix" {
  description = "(optional) - Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix."
  type        = string
  default     = null
}

variable "payload_format" {
  description = "(required) - The desired content of the Payload. One of \"JSON_API_V1\" or \"NONE\"."
  type        = string
}

variable "topic" {
  description = "(required) - The Cloud Pub/Sub topic to which this subscription publishes. Expects either the  topic name, assumed to belong to the default GCP provider project, or the project-level name,  i.e. projects/my-gcp-project/topics/my-topic or my-topic. If the project is not set in the provider, you will need to use the project-level name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_storage_notification" "this" {
  bucket             = var.bucket
  custom_attributes  = var.custom_attributes
  event_types        = var.event_types
  object_name_prefix = var.object_name_prefix
  payload_format     = var.payload_format
  topic              = var.topic
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_storage_notification.this.id
}

output "notification_id" {
  description = "returns a string"
  value       = google_storage_notification.this.notification_id
}

output "self_link" {
  description = "returns a string"
  value       = google_storage_notification.this.self_link
}

output "this" {
  value = google_storage_notification.this
}
```

[top](#index)