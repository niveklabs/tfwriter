# google_compute_network_peering

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
module "google_compute_network_peering" {
  source = "./modules/google/r/google_compute_network_peering"

  # export_custom_routes - (optional) is a type of bool
  export_custom_routes = null
  # export_subnet_routes_with_public_ip - (optional) is a type of bool
  export_subnet_routes_with_public_ip = null
  # import_custom_routes - (optional) is a type of bool
  import_custom_routes = null
  # import_subnet_routes_with_public_ip - (optional) is a type of bool
  import_subnet_routes_with_public_ip = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # peer_network - (required) is a type of string
  peer_network = null

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
  description = "(optional) - Whether to export the custom routes to the peer network. Defaults to false."
  type        = bool
  default     = null
}

variable "export_subnet_routes_with_public_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "import_custom_routes" {
  description = "(optional) - Whether to export the custom routes from the peer network. Defaults to false."
  type        = bool
  default     = null
}

variable "import_subnet_routes_with_public_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the peering."
  type        = string
}

variable "network" {
  description = "(required) - The primary network of the peering."
  type        = string
}

variable "peer_network" {
  description = "(required) - The peer network in the peering. The peer network may belong to a different project."
  type        = string
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
resource "google_compute_network_peering" "this" {
  # export_custom_routes - (optional) is a type of bool
  export_custom_routes = var.export_custom_routes
  # export_subnet_routes_with_public_ip - (optional) is a type of bool
  export_subnet_routes_with_public_ip = var.export_subnet_routes_with_public_ip
  # import_custom_routes - (optional) is a type of bool
  import_custom_routes = var.import_custom_routes
  # import_subnet_routes_with_public_ip - (optional) is a type of bool
  import_subnet_routes_with_public_ip = var.import_subnet_routes_with_public_ip
  # name - (required) is a type of string
  name = var.name
  # network - (required) is a type of string
  network = var.network
  # peer_network - (required) is a type of string
  peer_network = var.peer_network

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = google_compute_network_peering.this.id
}

output "state" {
  description = "returns a string"
  value       = google_compute_network_peering.this.state
}

output "state_details" {
  description = "returns a string"
  value       = google_compute_network_peering.this.state_details
}

output "this" {
  value = google_compute_network_peering.this
}
```

[top](#index)