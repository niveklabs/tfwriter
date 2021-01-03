# google_compute_router_nat

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_router_nat" {
  source = "./modules/google-beta/r/google_compute_router_nat"

  # drain_nat_ips - (optional) is a type of set of string
  drain_nat_ips = []
  # icmp_idle_timeout_sec - (optional) is a type of number
  icmp_idle_timeout_sec = null
  # min_ports_per_vm - (optional) is a type of number
  min_ports_per_vm = null
  # name - (required) is a type of string
  name = null
  # nat_ip_allocate_option - (required) is a type of string
  nat_ip_allocate_option = null
  # nat_ips - (optional) is a type of set of string
  nat_ips = []
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # router - (required) is a type of string
  router = null
  # source_subnetwork_ip_ranges_to_nat - (required) is a type of string
  source_subnetwork_ip_ranges_to_nat = null
  # tcp_established_idle_timeout_sec - (optional) is a type of number
  tcp_established_idle_timeout_sec = null
  # tcp_transitory_idle_timeout_sec - (optional) is a type of number
  tcp_transitory_idle_timeout_sec = null
  # udp_idle_timeout_sec - (optional) is a type of number
  udp_idle_timeout_sec = null

  log_config = [{
    enable = null
    filter = null
  }]

  subnetwork = [{
    name                     = null
    secondary_ip_range_names = []
    source_ip_ranges_to_nat  = []
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
variable "drain_nat_ips" {
  description = "(optional) - A list of URLs of the IP resources to be drained. These IPs must be\nvalid static external IPs that have been assigned to the NAT."
  type        = set(string)
  default     = null
}

variable "icmp_idle_timeout_sec" {
  description = "(optional) - Timeout (in seconds) for ICMP connections. Defaults to 30s if not set."
  type        = number
  default     = null
}

variable "min_ports_per_vm" {
  description = "(optional) - Minimum number of ports allocated to a VM from this NAT."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the NAT service. The name must be 1-63 characters long and\ncomply with RFC1035."
  type        = string
}

variable "nat_ip_allocate_option" {
  description = "(required) - How external IPs should be allocated for this NAT. Valid values are\n'AUTO_ONLY' for only allowing NAT IPs allocated by Google Cloud\nPlatform, or 'MANUAL_ONLY' for only user-allocated NAT IP addresses. Possible values: [\"MANUAL_ONLY\", \"AUTO_ONLY\"]"
  type        = string
}

variable "nat_ips" {
  description = "(optional) - Self-links of NAT IPs. Only valid if natIpAllocateOption\nis set to MANUAL_ONLY."
  type        = set(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the router and NAT reside."
  type        = string
  default     = null
}

variable "router" {
  description = "(required) - The name of the Cloud Router in which this NAT will be configured."
  type        = string
}

variable "source_subnetwork_ip_ranges_to_nat" {
  description = "(required) - How NAT should be configured per Subnetwork.\nIf 'ALL_SUBNETWORKS_ALL_IP_RANGES', all of the\nIP ranges in every Subnetwork are allowed to Nat.\nIf 'ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES', all of the primary IP\nranges in every Subnetwork are allowed to Nat.\n'LIST_OF_SUBNETWORKS': A list of Subnetworks are allowed to Nat\n(specified in the field subnetwork below). Note that if this field\ncontains ALL_SUBNETWORKS_ALL_IP_RANGES or\nALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any\nother RouterNat section in any Router for this network in this region. Possible values: [\"ALL_SUBNETWORKS_ALL_IP_RANGES\", \"ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES\", \"LIST_OF_SUBNETWORKS\"]"
  type        = string
}

variable "tcp_established_idle_timeout_sec" {
  description = "(optional) - Timeout (in seconds) for TCP established connections.\nDefaults to 1200s if not set."
  type        = number
  default     = null
}

variable "tcp_transitory_idle_timeout_sec" {
  description = "(optional) - Timeout (in seconds) for TCP transitory connections.\nDefaults to 30s if not set."
  type        = number
  default     = null
}

variable "udp_idle_timeout_sec" {
  description = "(optional) - Timeout (in seconds) for UDP connections. Defaults to 30s if not set."
  type        = number
  default     = null
}

variable "log_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable = bool
      filter = string
    }
  ))
  default = []
}

variable "subnetwork" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name                     = string
      secondary_ip_range_names = set(string)
      source_ip_ranges_to_nat  = set(string)
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
resource "google_compute_router_nat" "this" {
  drain_nat_ips                      = var.drain_nat_ips
  icmp_idle_timeout_sec              = var.icmp_idle_timeout_sec
  min_ports_per_vm                   = var.min_ports_per_vm
  name                               = var.name
  nat_ip_allocate_option             = var.nat_ip_allocate_option
  nat_ips                            = var.nat_ips
  project                            = var.project
  region                             = var.region
  router                             = var.router
  source_subnetwork_ip_ranges_to_nat = var.source_subnetwork_ip_ranges_to_nat
  tcp_established_idle_timeout_sec   = var.tcp_established_idle_timeout_sec
  tcp_transitory_idle_timeout_sec    = var.tcp_transitory_idle_timeout_sec
  udp_idle_timeout_sec               = var.udp_idle_timeout_sec

  dynamic "log_config" {
    for_each = var.log_config
    content {
      enable = log_config.value["enable"]
      filter = log_config.value["filter"]
    }
  }

  dynamic "subnetwork" {
    for_each = var.subnetwork
    content {
      name                     = subnetwork.value["name"]
      secondary_ip_range_names = subnetwork.value["secondary_ip_range_names"]
      source_ip_ranges_to_nat  = subnetwork.value["source_ip_ranges_to_nat"]
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
  value       = google_compute_router_nat.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_router_nat.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_router_nat.this.region
}

output "this" {
  value = google_compute_router_nat.this
}
```

[top](#index)