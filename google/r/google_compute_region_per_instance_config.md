# google_compute_region_per_instance_config

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
module "google_compute_region_per_instance_config" {
  source = "./modules/google/r/google_compute_region_per_instance_config"

  # minimal_action - (optional) is a type of string
  minimal_action = null
  # most_disruptive_allowed_action - (optional) is a type of string
  most_disruptive_allowed_action = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # region_instance_group_manager - (required) is a type of string
  region_instance_group_manager = null
  # remove_instance_state_on_destroy - (optional) is a type of bool
  remove_instance_state_on_destroy = null

  preserved_state = [{
    disk = [{
      delete_rule = null
      device_name = null
      mode        = null
      source      = null
    }]
    metadata = {}
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
variable "minimal_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "most_disruptive_allowed_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name for this per-instance config and its corresponding instance."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the containing instance group manager is located"
  type        = string
  default     = null
}

variable "region_instance_group_manager" {
  description = "(required) - The region instance group manager this instance config is part of."
  type        = string
}

variable "remove_instance_state_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "preserved_state" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disk = set(object(
        {
          delete_rule = string
          device_name = string
          mode        = string
          source      = string
        }
      ))
      metadata = map(string)
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
resource "google_compute_region_per_instance_config" "this" {
  # minimal_action - (optional) is a type of string
  minimal_action = var.minimal_action
  # most_disruptive_allowed_action - (optional) is a type of string
  most_disruptive_allowed_action = var.most_disruptive_allowed_action
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # region_instance_group_manager - (required) is a type of string
  region_instance_group_manager = var.region_instance_group_manager
  # remove_instance_state_on_destroy - (optional) is a type of bool
  remove_instance_state_on_destroy = var.remove_instance_state_on_destroy

  dynamic "preserved_state" {
    for_each = var.preserved_state
    content {
      # metadata - (optional) is a type of map of string
      metadata = preserved_state.value["metadata"]

      dynamic "disk" {
        for_each = preserved_state.value.disk
        content {
          # delete_rule - (optional) is a type of string
          delete_rule = disk.value["delete_rule"]
          # device_name - (required) is a type of string
          device_name = disk.value["device_name"]
          # mode - (optional) is a type of string
          mode = disk.value["mode"]
          # source - (required) is a type of string
          source = disk.value["source"]
        }
      }

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
  value       = google_compute_region_per_instance_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_per_instance_config.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_per_instance_config.this.region
}

output "this" {
  value = google_compute_region_per_instance_config.this
}
```

[top](#index)