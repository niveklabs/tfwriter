# google_game_services_game_server_deployment_rollout

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
module "google_game_services_game_server_deployment_rollout" {
  source = "./modules/google/r/google_game_services_game_server_deployment_rollout"

  # default_game_server_config - (required) is a type of string
  default_game_server_config = null
  # deployment_id - (required) is a type of string
  deployment_id = null
  # project - (optional) is a type of string
  project = null

  game_server_config_overrides = [{
    config_version = null
    realms_selector = [{
      realms = []
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

```hcl
variable "default_game_server_config" {
  description = "(required) - This field points to the game server config that is\napplied by default to all realms and clusters. For example,\n\n'projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config'."
  type        = string
}

variable "deployment_id" {
  description = "(required) - The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "game_server_config_overrides" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config_version = string
      realms_selector = list(object(
        {
          realms = list(string)
        }
      ))
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
resource "google_game_services_game_server_deployment_rollout" "this" {
  default_game_server_config = var.default_game_server_config
  deployment_id              = var.deployment_id
  project                    = var.project

  dynamic "game_server_config_overrides" {
    for_each = var.game_server_config_overrides
    content {
      config_version = game_server_config_overrides.value["config_version"]

      dynamic "realms_selector" {
        for_each = game_server_config_overrides.value.realms_selector
        content {
          realms = realms_selector.value["realms"]
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
  value       = google_game_services_game_server_deployment_rollout.this.id
}

output "name" {
  description = "returns a string"
  value       = google_game_services_game_server_deployment_rollout.this.name
}

output "project" {
  description = "returns a string"
  value       = google_game_services_game_server_deployment_rollout.this.project
}

output "this" {
  value = google_game_services_game_server_deployment_rollout.this
}
```

[top](#index)