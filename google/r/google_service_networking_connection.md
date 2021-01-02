# google_service_networking_connection

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
module "google_service_networking_connection" {
  source = "./modules/google/r/google_service_networking_connection"

  # network - (required) is a type of string
  network = null
  # reserved_peering_ranges - (required) is a type of list of string
  reserved_peering_ranges = []
  # service - (required) is a type of string
  service = null

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
variable "network" {
  description = "(required) - Name of VPC network connected with service producers using VPC peering."
  type        = string
}

variable "reserved_peering_ranges" {
  description = "(required) - Named IP address range(s) of PEERING type reserved for this service provider. Note that invoking this method with a different range when connection is already established will not reallocate already provisioned service producer subnetworks."
  type        = list(string)
}

variable "service" {
  description = "(required) - Provider peering service that is managing peering connectivity for a service provider organization. For Google services that support this functionality it is 'servicenetworking.googleapis.com'."
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
resource "google_service_networking_connection" "this" {
  network                 = var.network
  reserved_peering_ranges = var.reserved_peering_ranges
  service                 = var.service

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
  value       = google_service_networking_connection.this.id
}

output "peering" {
  description = "returns a string"
  value       = google_service_networking_connection.this.peering
}

output "this" {
  value = google_service_networking_connection.this
}
```

[top](#index)