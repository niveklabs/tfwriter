# google_compute_network

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
module "google_compute_network" {
  source = "./modules/google/r/google_compute_network"

  # auto_create_subnetworks - (optional) is a type of bool
  auto_create_subnetworks = null
  # delete_default_routes_on_create - (optional) is a type of bool
  delete_default_routes_on_create = null
  # description - (optional) is a type of string
  description = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # routing_mode - (optional) is a type of string
  routing_mode = null

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
variable "auto_create_subnetworks" {
  description = "(optional) - When set to 'true', the network is created in \"auto subnet mode\" and\nit will create a subnet for each region automatically across the\n'10.128.0.0/9' address range.\n\nWhen set to 'false', the network is created in \"custom subnet mode\" so\nthe user can explicitly connect subnetwork resources."
  type        = bool
  default     = null
}

variable "delete_default_routes_on_create" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource. The resource must be\nrecreated to modify this field."
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - Maximum Transmission Unit in bytes. The minimum value for this field is 1460\nand the maximum value is 1500 bytes."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "routing_mode" {
  description = "(optional) - The network-wide routing mode to use. If set to 'REGIONAL', this\nnetwork's cloud routers will only advertise routes with subnetworks\nof this network in the same region as the router. If set to 'GLOBAL',\nthis network's cloud routers will advertise routes with all\nsubnetworks of this network, across regions. Possible values: [\"REGIONAL\", \"GLOBAL\"]"
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
resource "google_compute_network" "this" {
  auto_create_subnetworks         = var.auto_create_subnetworks
  delete_default_routes_on_create = var.delete_default_routes_on_create
  description                     = var.description
  mtu                             = var.mtu
  name                            = var.name
  project                         = var.project
  routing_mode                    = var.routing_mode

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
output "gateway_ipv4" {
  description = "returns a string"
  value       = google_compute_network.this.gateway_ipv4
}

output "id" {
  description = "returns a string"
  value       = google_compute_network.this.id
}

output "mtu" {
  description = "returns a number"
  value       = google_compute_network.this.mtu
}

output "project" {
  description = "returns a string"
  value       = google_compute_network.this.project
}

output "routing_mode" {
  description = "returns a string"
  value       = google_compute_network.this.routing_mode
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_network.this.self_link
}

output "this" {
  value = google_compute_network.this
}
```

[top](#index)