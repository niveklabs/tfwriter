# google_app_engine_service_split_traffic

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
module "google_app_engine_service_split_traffic" {
  source = "./modules/google/r/google_app_engine_service_split_traffic"

  # migrate_traffic - (optional) is a type of bool
  migrate_traffic = null
  # project - (optional) is a type of string
  project = null
  # service - (required) is a type of string
  service = null

  split = [{
    allocations = {}
    shard_by    = null
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
variable "migrate_traffic" {
  description = "(optional) - If set to true traffic will be migrated to this version."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "(required) - The name of the service these settings apply to."
  type        = string
}

variable "split" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      allocations = map(string)
      shard_by    = string
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
resource "google_app_engine_service_split_traffic" "this" {
  # migrate_traffic - (optional) is a type of bool
  migrate_traffic = var.migrate_traffic
  # project - (optional) is a type of string
  project = var.project
  # service - (required) is a type of string
  service = var.service

  dynamic "split" {
    for_each = var.split
    content {
      # allocations - (required) is a type of map of string
      allocations = split.value["allocations"]
      # shard_by - (optional) is a type of string
      shard_by = split.value["shard_by"]
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
output "id" {
  description = "returns a string"
  value       = google_app_engine_service_split_traffic.this.id
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_service_split_traffic.this.project
}

output "this" {
  value = google_app_engine_service_split_traffic.this
}
```

[top](#index)