# google_compute_forwarding_rule

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_compute_forwarding_rule" {
  source = "./modules/google/d/google_compute_forwarding_rule"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - A reference to the region where the regional forwarding rule resides.\nThis field is not applicable to global forwarding rules."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_forwarding_rule" "this" {
  name    = var.name
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "all_ports" {
  description = "returns a bool"
  value       = data.google_compute_forwarding_rule.this.all_ports
}

output "allow_global_access" {
  description = "returns a bool"
  value       = data.google_compute_forwarding_rule.this.allow_global_access
}

output "backend_service" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.backend_service
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.creation_timestamp
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.ip_address
}

output "ip_protocol" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.ip_protocol
}

output "is_mirroring_collector" {
  description = "returns a bool"
  value       = data.google_compute_forwarding_rule.this.is_mirroring_collector
}

output "load_balancing_scheme" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.load_balancing_scheme
}

output "network" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.network
}

output "network_tier" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.network_tier
}

output "port_range" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.port_range
}

output "ports" {
  description = "returns a set of string"
  value       = data.google_compute_forwarding_rule.this.ports
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.self_link
}

output "service_label" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.service_label
}

output "service_name" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.service_name
}

output "subnetwork" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.subnetwork
}

output "target" {
  description = "returns a string"
  value       = data.google_compute_forwarding_rule.this.target
}

output "this" {
  value = google_compute_forwarding_rule.this
}
```

[top](#index)