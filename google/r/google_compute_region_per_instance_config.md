# google_compute_region_per_instance_config

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
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
  # region - (required) is a type of string
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

```hcl
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
  description = "(required) - Region where the containing instance group manager is located"
  type        = string
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_compute_region_per_instance_config" "this" {
  minimal_action                   = var.minimal_action
  most_disruptive_allowed_action   = var.most_disruptive_allowed_action
  name                             = var.name
  project                          = var.project
  region                           = var.region
  region_instance_group_manager    = var.region_instance_group_manager
  remove_instance_state_on_destroy = var.remove_instance_state_on_destroy

  dynamic "preserved_state" {
    for_each = var.preserved_state
    content {
      metadata = preserved_state.value["metadata"]

      dynamic "disk" {
        for_each = preserved_state.value.disk
        content {
          delete_rule = disk.value["delete_rule"]
          device_name = disk.value["device_name"]
          mode        = disk.value["mode"]
          source      = disk.value["source"]
        }
      }

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_compute_region_per_instance_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_per_instance_config.this.project
}

output "this" {
  value = google_compute_region_per_instance_config.this
}
```

[top](#index)