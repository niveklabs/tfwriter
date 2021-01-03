# google_compute_backend_service

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_compute_backend_service" {
  source = "./modules/google-beta/d/google_compute_backend_service"

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
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
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
data "google_compute_backend_service" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "affinity_cookie_ttl_sec" {
  description = "returns a number"
  value       = data.google_compute_backend_service.this.affinity_cookie_ttl_sec
}

output "backend" {
  description = "returns a set of object"
  value       = data.google_compute_backend_service.this.backend
}

output "cdn_policy" {
  description = "returns a list of object"
  value       = data.google_compute_backend_service.this.cdn_policy
}

output "circuit_breakers" {
  description = "returns a list of object"
  value       = data.google_compute_backend_service.this.circuit_breakers
}

output "connection_draining_timeout_sec" {
  description = "returns a number"
  value       = data.google_compute_backend_service.this.connection_draining_timeout_sec
}

output "consistent_hash" {
  description = "returns a list of object"
  value       = data.google_compute_backend_service.this.consistent_hash
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.creation_timestamp
}

output "custom_request_headers" {
  description = "returns a set of string"
  value       = data.google_compute_backend_service.this.custom_request_headers
}

output "custom_response_headers" {
  description = "returns a set of string"
  value       = data.google_compute_backend_service.this.custom_response_headers
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.description
}

output "enable_cdn" {
  description = "returns a bool"
  value       = data.google_compute_backend_service.this.enable_cdn
}

output "fingerprint" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.fingerprint
}

output "health_checks" {
  description = "returns a set of string"
  value       = data.google_compute_backend_service.this.health_checks
}

output "iap" {
  description = "returns a list of object"
  value       = data.google_compute_backend_service.this.iap
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.id
}

output "load_balancing_scheme" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.load_balancing_scheme
}

output "locality_lb_policy" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.locality_lb_policy
}

output "log_config" {
  description = "returns a list of object"
  value       = data.google_compute_backend_service.this.log_config
}

output "outlier_detection" {
  description = "returns a list of object"
  value       = data.google_compute_backend_service.this.outlier_detection
}

output "port_name" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.port_name
}

output "protocol" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.protocol
}

output "security_policy" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.security_policy
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.self_link
}

output "session_affinity" {
  description = "returns a string"
  value       = data.google_compute_backend_service.this.session_affinity
}

output "timeout_sec" {
  description = "returns a number"
  value       = data.google_compute_backend_service.this.timeout_sec
}

output "this" {
  value = google_compute_backend_service.this
}
```

[top](#index)