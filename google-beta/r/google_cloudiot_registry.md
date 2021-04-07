# google_cloudiot_registry

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
module "google_cloudiot_registry" {
  source = "./modules/google-beta/r/google_cloudiot_registry"

  # http_config - (optional) is a type of map of string
  http_config = {}
  # log_level - (optional) is a type of string
  log_level = null
  # mqtt_config - (optional) is a type of map of string
  mqtt_config = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # state_notification_config - (optional) is a type of map of string
  state_notification_config = {}

  credentials = [{
    public_key_certificate = {}
  }]

  event_notification_configs = [{
    pubsub_topic_name = null
    subfolder_matches = null
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
variable "http_config" {
  description = "(optional) - Activate or deactivate HTTP."
  type        = map(string)
  default     = null
}

variable "log_level" {
  description = "(optional) - The default logging verbosity for activity from devices in this\nregistry. Specifies which events should be written to logs. For\nexample, if the LogLevel is ERROR, only events that terminate in\nerrors will be logged. LogLevel is inclusive; enabling INFO logging\nwill also enable ERROR logging. Default value: \"NONE\" Possible values: [\"NONE\", \"ERROR\", \"INFO\", \"DEBUG\"]"
  type        = string
  default     = null
}

variable "mqtt_config" {
  description = "(optional) - Activate or deactivate MQTT."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - A unique name for the resource, required by device registry."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region in which the created registry should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "state_notification_config" {
  description = "(optional) - A PubSub topic to publish device state updates."
  type        = map(string)
  default     = null
}

variable "credentials" {
  description = "nested block: NestingList, min items: 0, max items: 10"
  type = set(object(
    {
      public_key_certificate = map(string)
    }
  ))
  default = []
}

variable "event_notification_configs" {
  description = "nested block: NestingList, min items: 0, max items: 10"
  type = set(object(
    {
      pubsub_topic_name = string
      subfolder_matches = string
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
resource "google_cloudiot_registry" "this" {
  # http_config - (optional) is a type of map of string
  http_config = var.http_config
  # log_level - (optional) is a type of string
  log_level = var.log_level
  # mqtt_config - (optional) is a type of map of string
  mqtt_config = var.mqtt_config
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # state_notification_config - (optional) is a type of map of string
  state_notification_config = var.state_notification_config

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # public_key_certificate - (required) is a type of map of string
      public_key_certificate = credentials.value["public_key_certificate"]
    }
  }

  dynamic "event_notification_configs" {
    for_each = var.event_notification_configs
    content {
      # pubsub_topic_name - (required) is a type of string
      pubsub_topic_name = event_notification_configs.value["pubsub_topic_name"]
      # subfolder_matches - (optional) is a type of string
      subfolder_matches = event_notification_configs.value["subfolder_matches"]
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
output "http_config" {
  description = "returns a map of string"
  value       = google_cloudiot_registry.this.http_config
}

output "id" {
  description = "returns a string"
  value       = google_cloudiot_registry.this.id
}

output "mqtt_config" {
  description = "returns a map of string"
  value       = google_cloudiot_registry.this.mqtt_config
}

output "project" {
  description = "returns a string"
  value       = google_cloudiot_registry.this.project
}

output "region" {
  description = "returns a string"
  value       = google_cloudiot_registry.this.region
}

output "this" {
  value = google_cloudiot_registry.this
}
```

[top](#index)