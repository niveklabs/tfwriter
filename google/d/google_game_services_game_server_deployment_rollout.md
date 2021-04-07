# google_game_services_game_server_deployment_rollout

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_game_services_game_server_deployment_rollout" {
  source = "./modules/google/d/google_game_services_game_server_deployment_rollout"

  # deployment_id - (required) is a type of string
  deployment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_id" {
  description = "(required) - The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_game_services_game_server_deployment_rollout" "this" {
  # deployment_id - (required) is a type of string
  deployment_id = var.deployment_id
}
```

[top](#index)

### Outputs

```terraform
output "default_game_server_config" {
  description = "returns a string"
  value       = data.google_game_services_game_server_deployment_rollout.this.default_game_server_config
}

output "game_server_config_overrides" {
  description = "returns a list of object"
  value       = data.google_game_services_game_server_deployment_rollout.this.game_server_config_overrides
}

output "id" {
  description = "returns a string"
  value       = data.google_game_services_game_server_deployment_rollout.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_game_services_game_server_deployment_rollout.this.name
}

output "project" {
  description = "returns a string"
  value       = data.google_game_services_game_server_deployment_rollout.this.project
}

output "this" {
  value = google_game_services_game_server_deployment_rollout.this
}
```

[top](#index)