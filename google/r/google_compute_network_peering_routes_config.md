# google_compute_network_peering_routes_config

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
module "google_compute_network_peering_routes_config" {
  source = "./modules/google/r/google_compute_network_peering_routes_config"

  # export_custom_routes - (required) is a type of bool
  export_custom_routes = null
  # import_custom_routes - (required) is a type of bool
  import_custom_routes = null
  # network - (required) is a type of string
  network = null
  # peering - (required) is a type of string
  peering = null
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

```terraform
variable "export_custom_routes" {
  description = "(required) - Whether to export the custom routes to the peer network."
  type        = bool
}

variable "import_custom_routes" {
  description = "(required) - Whether to import the custom routes to the peer network."
  type        = bool
}

variable "network" {
  description = "(required) - The name of the primary network for the peering."
  type        = string
}

variable "peering" {
  description = "(required) - Name of the peering."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "google_compute_network_peering_routes_config" "this" {
  export_custom_routes = var.export_custom_routes
  import_custom_routes = var.import_custom_routes
  network              = var.network
  peering              = var.peering
  project              = var.project

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
  value       = google_compute_network_peering_routes_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_network_peering_routes_config.this.project
}

output "this" {
  value = google_compute_network_peering_routes_config.this
}
```

[top](#index)