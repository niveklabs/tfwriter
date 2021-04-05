# google_pubsub_subscription

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
module "google_pubsub_subscription" {
  source = "./modules/google/r/google_pubsub_subscription"

  # ack_deadline_seconds - (optional) is a type of number
  ack_deadline_seconds = null
  # enable_message_ordering - (optional) is a type of bool
  enable_message_ordering = null
  # filter - (optional) is a type of string
  filter = null
  # labels - (optional) is a type of map of string
  labels = {}
  # message_retention_duration - (optional) is a type of string
  message_retention_duration = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # retain_acked_messages - (optional) is a type of bool
  retain_acked_messages = null
  # topic - (required) is a type of string
  topic = null

  dead_letter_policy = [{
    dead_letter_topic     = null
    max_delivery_attempts = null
  }]

  expiration_policy = [{
    ttl = null
  }]

  push_config = [{
    attributes = {}
    oidc_token = [{
      audience              = null
      service_account_email = null
    }]
    push_endpoint = null
  }]

  retry_policy = [{
    maximum_backoff = null
    minimum_backoff = null
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
variable "ack_deadline_seconds" {
  description = "(optional) - This value is the maximum time after a subscriber receives a message\nbefore the subscriber should acknowledge the message. After message\ndelivery but before the ack deadline expires and before the message is\nacknowledged, it is an outstanding message and will not be delivered\nagain during that time (on a best-effort basis).\n\nFor pull subscriptions, this value is used as the initial value for\nthe ack deadline. To override this value for a given message, call\nsubscriptions.modifyAckDeadline with the corresponding ackId if using\npull. The minimum custom deadline you can specify is 10 seconds. The\nmaximum custom deadline you can specify is 600 seconds (10 minutes).\nIf this parameter is 0, a default value of 10 seconds is used.\n\nFor push delivery, this value is also used to set the request timeout\nfor the call to the push endpoint.\n\nIf the subscriber never acknowledges the message, the Pub/Sub system\nwill eventually redeliver the message."
  type        = number
  default     = null
}

variable "enable_message_ordering" {
  description = "(optional) - If 'true', messages published with the same orderingKey in PubsubMessage will be delivered to\nthe subscribers in the order in which they are received by the Pub/Sub system. Otherwise, they\nmay be delivered in any order."
  type        = bool
  default     = null
}

variable "filter" {
  description = "(optional) - The subscription only delivers the messages that match the filter. \nPub/Sub automatically acknowledges the messages that don't match the filter. You can filter messages\nby their attributes. The maximum length of a filter is 256 bytes. After creating the subscription, \nyou can't modify the filter."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to this Subscription."
  type        = map(string)
  default     = null
}

variable "message_retention_duration" {
  description = "(optional) - How long to retain unacknowledged messages in the subscription's\nbacklog, from the moment a message is published. If\nretainAckedMessages is true, then this also configures the retention\nof acknowledged messages, and thus configures how far back in time a\nsubscriptions.seek can be done. Defaults to 7 days. Cannot be more\nthan 7 days ('\"604800s\"') or less than 10 minutes ('\"600s\"').\n\nA duration in seconds with up to nine fractional digits, terminated\nby 's'. Example: '\"600.5s\"'."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the subscription."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retain_acked_messages" {
  description = "(optional) - Indicates whether to retain acknowledged messages. If 'true', then\nmessages are not expunged from the subscription's backlog, even if\nthey are acknowledged, until they fall out of the\nmessageRetentionDuration window."
  type        = bool
  default     = null
}

variable "topic" {
  description = "(required) - A reference to a Topic resource."
  type        = string
}

variable "dead_letter_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dead_letter_topic     = string
      max_delivery_attempts = number
    }
  ))
  default = []
}

variable "expiration_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ttl = string
    }
  ))
  default = []
}

variable "push_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attributes = map(string)
      oidc_token = list(object(
        {
          audience              = string
          service_account_email = string
        }
      ))
      push_endpoint = string
    }
  ))
  default = []
}

variable "retry_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      maximum_backoff = string
      minimum_backoff = string
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
resource "google_pubsub_subscription" "this" {
  ack_deadline_seconds       = var.ack_deadline_seconds
  enable_message_ordering    = var.enable_message_ordering
  filter                     = var.filter
  labels                     = var.labels
  message_retention_duration = var.message_retention_duration
  name                       = var.name
  project                    = var.project
  retain_acked_messages      = var.retain_acked_messages
  topic                      = var.topic

  dynamic "dead_letter_policy" {
    for_each = var.dead_letter_policy
    content {
      dead_letter_topic     = dead_letter_policy.value["dead_letter_topic"]
      max_delivery_attempts = dead_letter_policy.value["max_delivery_attempts"]
    }
  }

  dynamic "expiration_policy" {
    for_each = var.expiration_policy
    content {
      ttl = expiration_policy.value["ttl"]
    }
  }

  dynamic "push_config" {
    for_each = var.push_config
    content {
      attributes    = push_config.value["attributes"]
      push_endpoint = push_config.value["push_endpoint"]

      dynamic "oidc_token" {
        for_each = push_config.value.oidc_token
        content {
          audience              = oidc_token.value["audience"]
          service_account_email = oidc_token.value["service_account_email"]
        }
      }

    }
  }

  dynamic "retry_policy" {
    for_each = var.retry_policy
    content {
      maximum_backoff = retry_policy.value["maximum_backoff"]
      minimum_backoff = retry_policy.value["minimum_backoff"]
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
output "ack_deadline_seconds" {
  description = "returns a number"
  value       = google_pubsub_subscription.this.ack_deadline_seconds
}

output "id" {
  description = "returns a string"
  value       = google_pubsub_subscription.this.id
}

output "path" {
  description = "returns a string"
  value       = google_pubsub_subscription.this.path
}

output "project" {
  description = "returns a string"
  value       = google_pubsub_subscription.this.project
}

output "this" {
  value = google_pubsub_subscription.this
}
```

[top](#index)