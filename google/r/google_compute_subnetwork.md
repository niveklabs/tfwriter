# google_compute_subnetwork

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_compute_subnetwork" {
  source = "./modules/google/r/google_compute_subnetwork"

  # description - (optional) is a type of string
  description = null
  # ip_cidr_range - (required) is a type of string
  ip_cidr_range = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # private_ip_google_access - (optional) is a type of bool
  private_ip_google_access = null
  # private_ipv6_google_access - (optional) is a type of string
  private_ipv6_google_access = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # secondary_ip_range - (optional) is a type of list of object
  secondary_ip_range = [{
    ip_cidr_range = null
    range_name    = null
  }]

  log_config = [{
    aggregation_interval = null
    filter_expr          = null
    flow_sampling        = null
    metadata             = null
    metadata_fields      = []
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

```hcl
variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource. This field can be set only at resource\ncreation time."
  type        = string
  default     = null
}

variable "ip_cidr_range" {
  description = "(required) - The range of internal addresses that are owned by this subnetwork.\nProvide this property when you create the subnetwork. For example,\n10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and\nnon-overlapping within a network. Only IPv4 is supported."
  type        = string
}

variable "name" {
  description = "(required) - The name of the resource, provided by the client when initially\ncreating the resource. The name must be 1-63 characters long, and\ncomply with RFC1035. Specifically, the name must be 1-63 characters\nlong and match the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which\nmeans the first character must be a lowercase letter, and all\nfollowing characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(required) - The network this subnet belongs to.\nOnly networks that are in the distributed mode can have subnetworks."
  type        = string
}

variable "private_ip_google_access" {
  description = "(optional) - When enabled, VMs in this subnetwork without external IP addresses can\naccess Google APIs and services by using Private Google Access."
  type        = bool
  default     = null
}

variable "private_ipv6_google_access" {
  description = "(optional) - The private IPv6 google access type for the VMs in this subnet."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The GCP region for this subnetwork."
  type        = string
  default     = null
}

variable "secondary_ip_range" {
  description = "(optional) - An array of configurations for secondary IP ranges for VM instances\ncontained in this subnetwork. The primary IP of such VM must belong\nto the primary ipCidrRange of the subnetwork. The alias IPs may belong\nto either primary or secondary ranges.\n\n**Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html) to avoid\nbreaking users during the 0.12 upgrade. To explicitly send a list\nof zero objects you must use the following syntax:\n'example=[]'\nFor more details about this behavior, see [this section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value)."
  type = list(object(
    {
      ip_cidr_range = string
      range_name    = string
    }
  ))
  default = null
}

variable "log_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aggregation_interval = string
      filter_expr          = string
      flow_sampling        = number
      metadata             = string
      metadata_fields      = set(string)
    }
  ))
  default = []
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
resource "google_compute_subnetwork" "this" {
  description                = var.description
  ip_cidr_range              = var.ip_cidr_range
  name                       = var.name
  network                    = var.network
  private_ip_google_access   = var.private_ip_google_access
  private_ipv6_google_access = var.private_ipv6_google_access
  project                    = var.project
  region                     = var.region
  secondary_ip_range         = var.secondary_ip_range

  dynamic "log_config" {
    for_each = var.log_config
    content {
      aggregation_interval = log_config.value["aggregation_interval"]
      filter_expr          = log_config.value["filter_expr"]
      flow_sampling        = log_config.value["flow_sampling"]
      metadata             = log_config.value["metadata"]
      metadata_fields      = log_config.value["metadata_fields"]
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

```hcl
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.creation_timestamp
}

output "fingerprint" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.fingerprint
}

output "gateway_address" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.gateway_address
}

output "id" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.id
}

output "private_ipv6_google_access" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.private_ipv6_google_access
}

output "project" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.region
}

output "secondary_ip_range" {
  description = "returns a list of object"
  value       = google_compute_subnetwork.this.secondary_ip_range
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_subnetwork.this.self_link
}

output "this" {
  value = google_compute_subnetwork.this
}
```

[top](#index)