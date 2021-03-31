# google_pubsub_lite_topic

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
module "google_pubsub_lite_topic" {
  source = "./modules/google/r/google_pubsub_lite_topic"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # zone - (optional) is a type of string
  zone = null

  partition_config = [{
    capacity = [{
      publish_mib_per_sec   = null
      subscribe_mib_per_sec = null
    }]
    count = null
  }]

  retention_config = [{
    per_partition_bytes = null
    period              = null
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
  description = "(required) - Name of the topic."
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

variable "zone" {
  description = "(optional) - The zone of the pubsub lite topic."
  type        = string
  default     = null
}

variable "partition_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      capacity = list(object(
        {
          publish_mib_per_sec   = number
          subscribe_mib_per_sec = number
        }
      ))
      count = number
    }
  ))
  default = []
}

variable "retention_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      per_partition_bytes = string
      period              = string
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
resource "google_pubsub_lite_topic" "this" {
  name    = var.name
  project = var.project
  region  = var.region
  zone    = var.zone

  dynamic "partition_config" {
    for_each = var.partition_config
    content {
      count = partition_config.value["count"]

      dynamic "capacity" {
        for_each = partition_config.value.capacity
        content {
          publish_mib_per_sec   = capacity.value["publish_mib_per_sec"]
          subscribe_mib_per_sec = capacity.value["subscribe_mib_per_sec"]
        }
      }

    }
  }

  dynamic "retention_config" {
    for_each = var.retention_config
    content {
      per_partition_bytes = retention_config.value["per_partition_bytes"]
      period              = retention_config.value["period"]
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
  value       = google_pubsub_lite_topic.this.id
}

output "project" {
  description = "returns a string"
  value       = google_pubsub_lite_topic.this.project
}

output "this" {
  value = google_pubsub_lite_topic.this
}
```

[top](#index)