# google_monitoring_notification_channel

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_monitoring_notification_channel" {
  source = "./modules/google/d/google_monitoring_notification_channel"

  # display_name - (optional) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null
  # type - (optional) is a type of string
  type = null
  # user_labels - (optional) is a type of map of string
  user_labels = {}
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional) - An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique name in order to make it easier to identify the channels in your project, though this is not enforced. The display name is limited to 512 Unicode characters."
  type        = string
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
  description = "(optional) - The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of valid values such as \"email\", \"slack\", etc..."
  type        = string
  default     = null
}

variable "user_labels" {
  description = "(optional) - User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor's schema, unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_monitoring_notification_channel" "this" {
  display_name = var.display_name
  labels       = var.labels
  project      = var.project
  type         = var.type
  user_labels  = var.user_labels
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_monitoring_notification_channel.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.google_monitoring_notification_channel.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.google_monitoring_notification_channel.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_monitoring_notification_channel.this.name
}

output "sensitive_labels" {
  description = "returns a list of object"
  value       = data.google_monitoring_notification_channel.this.sensitive_labels
}

output "verification_status" {
  description = "returns a string"
  value       = data.google_monitoring_notification_channel.this.verification_status
}

output "this" {
  value = google_monitoring_notification_channel.this
}
```

[top](#index)