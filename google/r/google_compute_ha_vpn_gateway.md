# google_compute_ha_vpn_gateway

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
module "google_compute_ha_vpn_gateway" {
  source = "./modules/google/r/google_compute_ha_vpn_gateway"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(required) - The network this VPN gateway is accepting traffic for."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region this gateway should sit in."
  type        = string
  default     = null
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
resource "google_compute_ha_vpn_gateway" "this" {
  description = var.description
  name        = var.name
  network     = var.network
  project     = var.project
  region      = var.region

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
  value       = google_compute_ha_vpn_gateway.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_ha_vpn_gateway.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_ha_vpn_gateway.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_ha_vpn_gateway.this.self_link
}

output "vpn_interfaces" {
  description = "returns a list of object"
  value       = google_compute_ha_vpn_gateway.this.vpn_interfaces
}

output "this" {
  value = google_compute_ha_vpn_gateway.this
}
```

[top](#index)