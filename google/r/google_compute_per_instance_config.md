# google_compute_per_instance_config

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_compute_per_instance_config" {
  source = "./modules/google/r/google_compute_per_instance_config"

  # instance_group_manager - (required) is a type of string
  instance_group_manager = null
  # minimal_action - (optional) is a type of string
  minimal_action = null
  # most_disruptive_allowed_action - (optional) is a type of string
  most_disruptive_allowed_action = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # remove_instance_state_on_destroy - (optional) is a type of bool
  remove_instance_state_on_destroy = null
  # zone - (required) is a type of string
  zone = null

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
variable "instance_group_manager" {
  description = "(required) - The instance group manager this instance config is part of."
  type        = string
}

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

variable "remove_instance_state_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "zone" {
  description = "(required) - Zone where the containing instance group manager is located"
  type        = string
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
resource "google_compute_per_instance_config" "this" {
  instance_group_manager           = var.instance_group_manager
  minimal_action                   = var.minimal_action
  most_disruptive_allowed_action   = var.most_disruptive_allowed_action
  name                             = var.name
  project                          = var.project
  remove_instance_state_on_destroy = var.remove_instance_state_on_destroy
  zone                             = var.zone

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
  value       = google_compute_per_instance_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_per_instance_config.this.project
}

output "this" {
  value = google_compute_per_instance_config.this
}
```

[top](#index)