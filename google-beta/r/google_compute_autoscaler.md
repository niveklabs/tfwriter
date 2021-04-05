# google_compute_autoscaler

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
module "google_compute_autoscaler" {
  source = "./modules/google-beta/r/google_compute_autoscaler"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # target - (required) is a type of string
  target = null
  # zone - (optional) is a type of string
  zone = null

  autoscaling_policy = [{
    cooldown_period = null
    cpu_utilization = [{
      predictive_method = null
      target            = null
    }]
    load_balancing_utilization = [{
      target = null
    }]
    max_replicas = null
    metric = [{
      filter                     = null
      name                       = null
      single_instance_assignment = null
      target                     = null
      type                       = null
    }]
    min_replicas = null
    mode         = null
    scale_down_control = [{
      max_scaled_down_replicas = [{
        fixed   = null
        percent = null
      }]
      time_window_sec = null
    }]
    scale_in_control = [{
      max_scaled_in_replicas = [{
        fixed   = null
        percent = null
      }]
      time_window_sec = null
    }]
    scaling_schedules = [{
      description           = null
      disabled              = null
      duration_sec          = null
      min_required_replicas = null
      name                  = null
      schedule              = null
      time_zone             = null
    }]
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
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. The name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(required) - URL of the managed instance group that this autoscaler will scale."
  type        = string
}

variable "zone" {
  description = "(optional) - URL of the zone where the instance group resides."
  type        = string
  default     = null
}

variable "autoscaling_policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cooldown_period = number
      cpu_utilization = list(object(
        {
          predictive_method = string
          target            = number
        }
      ))
      load_balancing_utilization = list(object(
        {
          target = number
        }
      ))
      max_replicas = number
      metric = list(object(
        {
          filter                     = string
          name                       = string
          single_instance_assignment = number
          target                     = number
          type                       = string
        }
      ))
      min_replicas = number
      mode         = string
      scale_down_control = list(object(
        {
          max_scaled_down_replicas = list(object(
            {
              fixed   = number
              percent = number
            }
          ))
          time_window_sec = number
        }
      ))
      scale_in_control = list(object(
        {
          max_scaled_in_replicas = list(object(
            {
              fixed   = number
              percent = number
            }
          ))
          time_window_sec = number
        }
      ))
      scaling_schedules = set(object(
        {
          description           = string
          disabled              = bool
          duration_sec          = number
          min_required_replicas = number
          name                  = string
          schedule              = string
          time_zone             = string
        }
      ))
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
resource "google_compute_autoscaler" "this" {
  description = var.description
  name        = var.name
  project     = var.project
  target      = var.target
  zone        = var.zone

  dynamic "autoscaling_policy" {
    for_each = var.autoscaling_policy
    content {
      cooldown_period = autoscaling_policy.value["cooldown_period"]
      max_replicas    = autoscaling_policy.value["max_replicas"]
      min_replicas    = autoscaling_policy.value["min_replicas"]
      mode            = autoscaling_policy.value["mode"]

      dynamic "cpu_utilization" {
        for_each = autoscaling_policy.value.cpu_utilization
        content {
          predictive_method = cpu_utilization.value["predictive_method"]
          target            = cpu_utilization.value["target"]
        }
      }

      dynamic "load_balancing_utilization" {
        for_each = autoscaling_policy.value.load_balancing_utilization
        content {
          target = load_balancing_utilization.value["target"]
        }
      }

      dynamic "metric" {
        for_each = autoscaling_policy.value.metric
        content {
          filter                     = metric.value["filter"]
          name                       = metric.value["name"]
          single_instance_assignment = metric.value["single_instance_assignment"]
          target                     = metric.value["target"]
          type                       = metric.value["type"]
        }
      }

      dynamic "scale_down_control" {
        for_each = autoscaling_policy.value.scale_down_control
        content {
          time_window_sec = scale_down_control.value["time_window_sec"]

          dynamic "max_scaled_down_replicas" {
            for_each = scale_down_control.value.max_scaled_down_replicas
            content {
              fixed   = max_scaled_down_replicas.value["fixed"]
              percent = max_scaled_down_replicas.value["percent"]
            }
          }

        }
      }

      dynamic "scale_in_control" {
        for_each = autoscaling_policy.value.scale_in_control
        content {
          time_window_sec = scale_in_control.value["time_window_sec"]

          dynamic "max_scaled_in_replicas" {
            for_each = scale_in_control.value.max_scaled_in_replicas
            content {
              fixed   = max_scaled_in_replicas.value["fixed"]
              percent = max_scaled_in_replicas.value["percent"]
            }
          }

        }
      }

      dynamic "scaling_schedules" {
        for_each = autoscaling_policy.value.scaling_schedules
        content {
          description           = scaling_schedules.value["description"]
          disabled              = scaling_schedules.value["disabled"]
          duration_sec          = scaling_schedules.value["duration_sec"]
          min_required_replicas = scaling_schedules.value["min_required_replicas"]
          name                  = scaling_schedules.value["name"]
          schedule              = scaling_schedules.value["schedule"]
          time_zone             = scaling_schedules.value["time_zone"]
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

```terraform
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_autoscaler.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_autoscaler.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_autoscaler.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_autoscaler.this.self_link
}

output "zone" {
  description = "returns a string"
  value       = google_compute_autoscaler.this.zone
}

output "this" {
  value = google_compute_autoscaler.this
}
```

[top](#index)