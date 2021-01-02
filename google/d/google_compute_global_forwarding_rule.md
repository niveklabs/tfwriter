# google_compute_global_forwarding_rule

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_global_forwarding_rule" {
  source = "./modules/google/d/google_compute_global_forwarding_rule"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
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
```

[top](#index)

### Datasource

```terraform
data "google_compute_global_forwarding_rule" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.ip_address
}

output "ip_protocol" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.ip_protocol
}

output "ip_version" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.ip_version
}

output "load_balancing_scheme" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.load_balancing_scheme
}

output "metadata_filters" {
  description = "returns a list of object"
  value       = data.google_compute_global_forwarding_rule.this.metadata_filters
}

output "port_range" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.port_range
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.self_link
}

output "target" {
  description = "returns a string"
  value       = data.google_compute_global_forwarding_rule.this.target
}

output "this" {
  value = google_compute_global_forwarding_rule.this
}
```

[top](#index)