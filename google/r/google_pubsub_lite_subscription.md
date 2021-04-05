# google_pubsub_lite_subscription

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
module "google_pubsub_lite_subscription" {
  source = "./modules/google/r/google_pubsub_lite_subscription"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # topic - (required) is a type of string
  topic = null
  # zone - (optional) is a type of string
  zone = null

  delivery_config = [{
    delivery_requirement = null
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
variable "name" {
  description = "(required) - Name of the subscription."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region of the pubsub lite topic."
  type        = string
  default     = null
}

variable "topic" {
  description = "(required) - A reference to a Topic resource."
  type        = string
}

variable "zone" {
  description = "(optional) - The zone of the pubsub lite topic."
  type        = string
  default     = null
}

variable "delivery_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delivery_requirement = string
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
resource "google_pubsub_lite_subscription" "this" {
  name    = var.name
  project = var.project
  region  = var.region
  topic   = var.topic
  zone    = var.zone

  dynamic "delivery_config" {
    for_each = var.delivery_config
    content {
      delivery_requirement = delivery_config.value["delivery_requirement"]
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
  value       = google_pubsub_lite_subscription.this.id
}

output "project" {
  description = "returns a string"
  value       = google_pubsub_lite_subscription.this.project
}

output "this" {
  value = google_pubsub_lite_subscription.this
}
```

[top](#index)