# google_bigtable_app_profile

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
module "google_bigtable_app_profile" {
  source = "./modules/google/r/google_bigtable_app_profile"

  # app_profile_id - (required) is a type of string
  app_profile_id = null
  # description - (optional) is a type of string
  description = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # instance - (optional) is a type of string
  instance = null
  # multi_cluster_routing_use_any - (optional) is a type of bool
  multi_cluster_routing_use_any = null
  # project - (optional) is a type of string
  project = null

  single_cluster_routing = [{
    allow_transactional_writes = null
    cluster_id                 = null
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
variable "app_profile_id" {
  description = "(required) - The unique name of the app profile in the form '[_a-zA-Z0-9][-_.a-zA-Z0-9]*'."
  type        = string
}

variable "description" {
  description = "(optional) - Long form description of the use case for this app profile."
  type        = string
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - If true, ignore safety checks when deleting/updating the app profile."
  type        = bool
  default     = null
}

variable "instance" {
  description = "(optional) - The name of the instance to create the app profile within."
  type        = string
  default     = null
}

variable "multi_cluster_routing_use_any" {
  description = "(optional) - If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest cluster that is available\nin the event of transient errors or delays. Clusters in a region are considered equidistant. Choosing this option sacrifices read-your-writes\nconsistency to improve availability."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_cluster_routing" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_transactional_writes = bool
      cluster_id                 = string
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
resource "google_bigtable_app_profile" "this" {
  app_profile_id                = var.app_profile_id
  description                   = var.description
  ignore_warnings               = var.ignore_warnings
  instance                      = var.instance
  multi_cluster_routing_use_any = var.multi_cluster_routing_use_any
  project                       = var.project

  dynamic "single_cluster_routing" {
    for_each = var.single_cluster_routing
    content {
      allow_transactional_writes = single_cluster_routing.value["allow_transactional_writes"]
      cluster_id                 = single_cluster_routing.value["cluster_id"]
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
  value       = google_bigtable_app_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = google_bigtable_app_profile.this.name
}

output "project" {
  description = "returns a string"
  value       = google_bigtable_app_profile.this.project
}

output "this" {
  value = google_bigtable_app_profile.this
}
```

[top](#index)