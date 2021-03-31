# google_monitoring_notification_channel

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_monitoring_notification_channel" {
  source = "./modules/google/r/google_monitoring_notification_channel"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null
  # type - (required) is a type of string
  type = null
  # user_labels - (optional) is a type of map of string
  user_labels = {}

  sensitive_labels = [{
    auth_token  = null
    password    = null
    service_key = null
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
variable "description" {
  description = "(optional) - An optional human-readable description of this notification channel. This description may provide additional details, beyond the display name, for the channel. This may not exceed 1024 Unicode characters."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique name in order to make it easier to identify the channels in your project, though this is not enforced. The display name is limited to 512 Unicode characters."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of notifications to a particular channel without removing the channel from all alerting policies that reference the channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the same set of alerting policies on the channel at some point in the future."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Configuration fields that define the channel and its behavior. The\npermissible and required labels are specified in the\nNotificationChannelDescriptor corresponding to the type field.\n\nLabels with sensitive data are obfuscated by the API and therefore Terraform cannot\ndetermine if there are upstream changes to these fields. They can also be configured via\nthe sensitive_labels block, but cannot be configured in both places."
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of valid values such as \"email\", \"slack\", etc..."
  type        = string
}

variable "user_labels" {
  description = "(optional) - User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor's schema, unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter."
  type        = map(string)
  default     = null
}

variable "sensitive_labels" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_token  = string
      password    = string
      service_key = string
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
resource "google_monitoring_notification_channel" "this" {
  description  = var.description
  display_name = var.display_name
  enabled      = var.enabled
  labels       = var.labels
  project      = var.project
  type         = var.type
  user_labels  = var.user_labels

  dynamic "sensitive_labels" {
    for_each = var.sensitive_labels
    content {
      auth_token  = sensitive_labels.value["auth_token"]
      password    = sensitive_labels.value["password"]
      service_key = sensitive_labels.value["service_key"]
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
  value       = google_monitoring_notification_channel.this.id
}

output "name" {
  description = "returns a string"
  value       = google_monitoring_notification_channel.this.name
}

output "project" {
  description = "returns a string"
  value       = google_monitoring_notification_channel.this.project
}

output "verification_status" {
  description = "returns a string"
  value       = google_monitoring_notification_channel.this.verification_status
}

output "this" {
  value = google_monitoring_notification_channel.this
}
```

[top](#index)