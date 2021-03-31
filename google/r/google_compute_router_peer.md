# google_compute_router_peer

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
module "google_compute_router_peer" {
  source = "./modules/google/r/google_compute_router_peer"

  # advertise_mode - (optional) is a type of string
  advertise_mode = null
  # advertised_groups - (optional) is a type of list of string
  advertised_groups = []
  # advertised_route_priority - (optional) is a type of number
  advertised_route_priority = null
  # interface - (required) is a type of string
  interface = null
  # name - (required) is a type of string
  name = null
  # peer_asn - (required) is a type of number
  peer_asn = null
  # peer_ip_address - (required) is a type of string
  peer_ip_address = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # router - (required) is a type of string
  router = null

  advertised_ip_ranges = [{
    description = null
    range       = null
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
variable "advertise_mode" {
  description = "(optional) - User-specified flag to indicate which mode to use for advertisement.\nValid values of this enum field are: 'DEFAULT', 'CUSTOM' Default value: \"DEFAULT\" Possible values: [\"DEFAULT\", \"CUSTOM\"]"
  type        = string
  default     = null
}

variable "advertised_groups" {
  description = "(optional) - User-specified list of prefix groups to advertise in custom\nmode, which can take one of the following options:\n\n* 'ALL_SUBNETS': Advertises all available subnets, including peer VPC subnets.\n* 'ALL_VPC_SUBNETS': Advertises the router's own VPC subnets.\n* 'ALL_PEER_VPC_SUBNETS': Advertises peer subnets of the router's VPC network.\n\n\nNote that this field can only be populated if advertiseMode is 'CUSTOM'\nand overrides the list defined for the router (in the \"bgp\" message).\nThese groups are advertised in addition to any specified prefixes.\nLeave this field blank to advertise no custom groups."
  type        = list(string)
  default     = null
}

variable "advertised_route_priority" {
  description = "(optional) - The priority of routes advertised to this BGP peer.\nWhere there is more than one matching route of maximum\nlength, the routes with the lowest priority value win."
  type        = number
  default     = null
}

variable "interface" {
  description = "(required) - Name of the interface the BGP peer is associated with."
  type        = string
}

variable "name" {
  description = "(required) - Name of this BGP peer. The name must be 1-63 characters long,\nand comply with RFC1035. Specifically, the name must be 1-63 characters\nlong and match the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which\nmeans the first character must be a lowercase letter, and all\nfollowing characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "peer_asn" {
  description = "(required) - Peer BGP Autonomous System Number (ASN).\nEach BGP interface may use a different value."
  type        = number
}

variable "peer_ip_address" {
  description = "(required) - IP address of the BGP interface outside Google Cloud Platform.\nOnly IPv4 is supported."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the router and BgpPeer reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "router" {
  description = "(required) - The name of the Cloud Router in which this BgpPeer will be configured."
  type        = string
}

variable "advertised_ip_ranges" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      range       = string
    }
  ))
  default = []
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
resource "google_compute_router_peer" "this" {
  advertise_mode            = var.advertise_mode
  advertised_groups         = var.advertised_groups
  advertised_route_priority = var.advertised_route_priority
  interface                 = var.interface
  name                      = var.name
  peer_asn                  = var.peer_asn
  peer_ip_address           = var.peer_ip_address
  project                   = var.project
  region                    = var.region
  router                    = var.router

  dynamic "advertised_ip_ranges" {
    for_each = var.advertised_ip_ranges
    content {
      description = advertised_ip_ranges.value["description"]
      range       = advertised_ip_ranges.value["range"]
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
  value       = google_compute_router_peer.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = google_compute_router_peer.this.ip_address
}

output "management_type" {
  description = "returns a string"
  value       = google_compute_router_peer.this.management_type
}

output "project" {
  description = "returns a string"
  value       = google_compute_router_peer.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_router_peer.this.region
}

output "this" {
  value = google_compute_router_peer.this
}
```

[top](#index)