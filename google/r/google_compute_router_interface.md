# google_compute_router_interface

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
module "google_compute_router_interface" {
  source = "./modules/google/r/google_compute_router_interface"

  # interconnect_attachment - (optional) is a type of string
  interconnect_attachment = null
  # ip_range - (optional) is a type of string
  ip_range = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # router - (required) is a type of string
  router = null
  # vpn_tunnel - (optional) is a type of string
  vpn_tunnel = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "interconnect_attachment" {
  description = "(optional) - The name or resource link to the VLAN interconnect for this interface. Changing this forces a new interface to be created. Only one of vpn_tunnel and interconnect_attachment can be specified."
  type        = string
  default     = null
}

variable "ip_range" {
  description = "(optional) - IP address and range of the interface. The IP range must be in the RFC3927 link-local IP space. Changing this forces a new interface to be created."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - A unique name for the interface, required by GCE. Changing this forces a new interface to be created."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which this interface's router belongs. If it is not provided, the provider project is used. Changing this forces a new interface to be created."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region this interface's router sits in. If not specified, the project region will be used. Changing this forces a new interface to be created."
  type        = string
  default     = null
}

variable "router" {
  description = "(required) - The name of the router this interface will be attached to. Changing this forces a new interface to be created."
  type        = string
}

variable "vpn_tunnel" {
  description = "(optional) - The name or resource link to the VPN tunnel this interface will be linked to. Changing this forces a new interface to be created. Only one of vpn_tunnel and interconnect_attachment can be specified."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
resource "google_compute_router_interface" "this" {
  interconnect_attachment = var.interconnect_attachment
  ip_range                = var.ip_range
  name                    = var.name
  project                 = var.project
  region                  = var.region
  router                  = var.router
  vpn_tunnel              = var.vpn_tunnel

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
  value       = google_compute_router_interface.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_router_interface.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_router_interface.this.region
}

output "this" {
  value = google_compute_router_interface.this
}
```

[top](#index)