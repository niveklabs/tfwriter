# spotinst_ocean_gke_import

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_ocean_gke_import" {
  source = "./modules/spotinst/r/spotinst_ocean_gke_import"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # location - (required) is a type of string
  location = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # whitelist - (optional) is a type of list of string
  whitelist = []

  autoscaler = [{
    auto_headroom_percentage = null
    cooldown                 = null
    down = [{
      evaluation_periods        = null
      max_scale_down_percentage = null
    }]
    headroom = [{
      cpu_per_unit    = null
      gpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    is_auto_config = null
    is_enabled     = null
    resource_limits = [{
      max_memory_gib = null
      max_vcpu       = null
    }]
  }]

  backend_services = [{
    location_type = null
    named_ports = [{
      name  = null
      ports = []
    }]
    scheme       = null
    service_name = null
  }]

  scheduled_task = [{
    shutdown_hours = [{
      is_enabled   = null
      time_windows = []
    }]
    tasks = [{
      batch_size_percentage = null
      cron_expression       = null
      is_enabled            = null
      task_type             = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "max_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "whitelist" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "autoscaler" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_headroom_percentage = number
      cooldown                 = number
      down = list(object(
        {
          evaluation_periods        = number
          max_scale_down_percentage = number
        }
      ))
      headroom = list(object(
        {
          cpu_per_unit    = number
          gpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      is_auto_config = bool
      is_enabled     = bool
      resource_limits = list(object(
        {
          max_memory_gib = number
          max_vcpu       = number
        }
      ))
    }
  ))
  default = []
}

variable "backend_services" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      location_type = string
      named_ports = set(object(
        {
          name  = string
          ports = list(string)
        }
      ))
      scheme       = string
      service_name = string
    }
  ))
  default = []
}

variable "scheduled_task" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      shutdown_hours = list(object(
        {
          is_enabled   = bool
          time_windows = list(string)
        }
      ))
      tasks = list(object(
        {
          batch_size_percentage = number
          cron_expression       = string
          is_enabled            = bool
          task_type             = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_ocean_gke_import" "this" {
  cluster_name     = var.cluster_name
  desired_capacity = var.desired_capacity
  location         = var.location
  max_size         = var.max_size
  min_size         = var.min_size
  whitelist        = var.whitelist

  dynamic "autoscaler" {
    for_each = var.autoscaler
    content {
      auto_headroom_percentage = autoscaler.value["auto_headroom_percentage"]
      cooldown                 = autoscaler.value["cooldown"]
      is_auto_config           = autoscaler.value["is_auto_config"]
      is_enabled               = autoscaler.value["is_enabled"]

      dynamic "down" {
        for_each = autoscaler.value.down
        content {
          evaluation_periods        = down.value["evaluation_periods"]
          max_scale_down_percentage = down.value["max_scale_down_percentage"]
        }
      }

      dynamic "headroom" {
        for_each = autoscaler.value.headroom
        content {
          cpu_per_unit    = headroom.value["cpu_per_unit"]
          gpu_per_unit    = headroom.value["gpu_per_unit"]
          memory_per_unit = headroom.value["memory_per_unit"]
          num_of_units    = headroom.value["num_of_units"]
        }
      }

      dynamic "resource_limits" {
        for_each = autoscaler.value.resource_limits
        content {
          max_memory_gib = resource_limits.value["max_memory_gib"]
          max_vcpu       = resource_limits.value["max_vcpu"]
        }
      }

    }
  }

  dynamic "backend_services" {
    for_each = var.backend_services
    content {
      location_type = backend_services.value["location_type"]
      scheme        = backend_services.value["scheme"]
      service_name  = backend_services.value["service_name"]

      dynamic "named_ports" {
        for_each = backend_services.value.named_ports
        content {
          name  = named_ports.value["name"]
          ports = named_ports.value["ports"]
        }
      }

    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {

      dynamic "shutdown_hours" {
        for_each = scheduled_task.value.shutdown_hours
        content {
          is_enabled   = shutdown_hours.value["is_enabled"]
          time_windows = shutdown_hours.value["time_windows"]
        }
      }

      dynamic "tasks" {
        for_each = scheduled_task.value.tasks
        content {
          batch_size_percentage = tasks.value["batch_size_percentage"]
          cron_expression       = tasks.value["cron_expression"]
          is_enabled            = tasks.value["is_enabled"]
          task_type             = tasks.value["task_type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_controller_id" {
  description = "returns a string"
  value       = spotinst_ocean_gke_import.this.cluster_controller_id
}

output "desired_capacity" {
  description = "returns a number"
  value       = spotinst_ocean_gke_import.this.desired_capacity
}

output "id" {
  description = "returns a string"
  value       = spotinst_ocean_gke_import.this.id
}

output "max_size" {
  description = "returns a number"
  value       = spotinst_ocean_gke_import.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = spotinst_ocean_gke_import.this.min_size
}

output "this" {
  value = spotinst_ocean_gke_import.this
}
```

[top](#index)