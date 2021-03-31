# google_game_services_game_server_config

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
module "google_game_services_game_server_config" {
  source = "./modules/google/r/google_game_services_game_server_config"

  # config_id - (required) is a type of string
  config_id = null
  # deployment_id - (required) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null

  fleet_configs = [{
    fleet_spec = null
    name       = null
  }]

  scaling_configs = [{
    fleet_autoscaler_spec = null
    name                  = null
    schedules = [{
      cron_job_duration = null
      cron_spec         = null
      end_time          = null
      start_time        = null
    }]
    selectors = [{
      labels = {}
    }]
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required) - A unique id for the deployment config."
  type        = string
}

variable "deployment_id" {
  description = "(required) - A unique id for the deployment."
  type        = string
}

variable "description" {
  description = "(optional) - The description of the game server config."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The labels associated with this game server config. Each label is a\nkey-value pair."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - Location of the Deployment."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fleet_configs" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      fleet_spec = string
      name       = string
    }
  ))
}

variable "scaling_configs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      fleet_autoscaler_spec = string
      name                  = string
      schedules = list(object(
        {
          cron_job_duration = string
          cron_spec         = string
          end_time          = string
          start_time        = string
        }
      ))
      selectors = list(object(
        {
          labels = map(string)
        }
      ))
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_game_services_game_server_config" "this" {
  config_id     = var.config_id
  deployment_id = var.deployment_id
  description   = var.description
  labels        = var.labels
  location      = var.location
  project       = var.project

  dynamic "fleet_configs" {
    for_each = var.fleet_configs
    content {
      fleet_spec = fleet_configs.value["fleet_spec"]
      name       = fleet_configs.value["name"]
    }
  }

  dynamic "scaling_configs" {
    for_each = var.scaling_configs
    content {
      fleet_autoscaler_spec = scaling_configs.value["fleet_autoscaler_spec"]
      name                  = scaling_configs.value["name"]

      dynamic "schedules" {
        for_each = scaling_configs.value.schedules
        content {
          cron_job_duration = schedules.value["cron_job_duration"]
          cron_spec         = schedules.value["cron_spec"]
          end_time          = schedules.value["end_time"]
          start_time        = schedules.value["start_time"]
        }
      }

      dynamic "selectors" {
        for_each = scaling_configs.value.selectors
        content {
          labels = selectors.value["labels"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_game_services_game_server_config.this.id
}

output "name" {
  description = "returns a string"
  value       = google_game_services_game_server_config.this.name
}

output "project" {
  description = "returns a string"
  value       = google_game_services_game_server_config.this.project
}

output "this" {
  value = google_game_services_game_server_config.this
}
```

[top](#index)