# google_game_services_game_server_deployment

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
module "google_game_services_game_server_deployment" {
  source = "./modules/google/r/google_game_services_game_server_deployment"

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
variable "deployment_id" {
  description = "(required) - A unique id for the deployment."
  type        = string
}

variable "description" {
  description = "(optional) - Human readable description of the game server deployment."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The labels associated with this game server deployment. Each label is a\nkey-value pair."
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
resource "google_game_services_game_server_deployment" "this" {
  deployment_id = var.deployment_id
  description   = var.description
  labels        = var.labels
  location      = var.location
  project       = var.project

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
  value       = google_game_services_game_server_deployment.this.id
}

output "name" {
  description = "returns a string"
  value       = google_game_services_game_server_deployment.this.name
}

output "project" {
  description = "returns a string"
  value       = google_game_services_game_server_deployment.this.project
}

output "this" {
  value = google_game_services_game_server_deployment.this
}
```

[top](#index)