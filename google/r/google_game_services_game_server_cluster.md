# google_game_services_game_server_cluster

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_game_services_game_server_cluster" {
  source = "./modules/google/r/google_game_services_game_server_cluster"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
  # realm_id - (required) is a type of string
  realm_id = null

  connection_info = [{
    gke_cluster_reference = [{
      cluster = null
    }]
    namespace = null
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
variable "cluster_id" {
  description = "(required) - Required. The resource name of the game server cluster"
  type        = string
}

variable "description" {
  description = "(optional) - Human readable description of the cluster."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The labels associated with this game server cluster. Each label is a\nkey-value pair."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - Location of the Cluster."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "realm_id" {
  description = "(required) - The realm id of the game server realm."
  type        = string
}

variable "connection_info" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      gke_cluster_reference = list(object(
        {
          cluster = string
        }
      ))
      namespace = string
    }
  ))
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

```terraform
resource "google_game_services_game_server_cluster" "this" {
  cluster_id  = var.cluster_id
  description = var.description
  labels      = var.labels
  location    = var.location
  project     = var.project
  realm_id    = var.realm_id

  dynamic "connection_info" {
    for_each = var.connection_info
    content {
      namespace = connection_info.value["namespace"]

      dynamic "gke_cluster_reference" {
        for_each = connection_info.value.gke_cluster_reference
        content {
          cluster = gke_cluster_reference.value["cluster"]
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
output "id" {
  description = "returns a string"
  value       = google_game_services_game_server_cluster.this.id
}

output "name" {
  description = "returns a string"
  value       = google_game_services_game_server_cluster.this.name
}

output "project" {
  description = "returns a string"
  value       = google_game_services_game_server_cluster.this.project
}

output "this" {
  value = google_game_services_game_server_cluster.this
}
```

[top](#index)