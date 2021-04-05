# google_compute_health_check

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_health_check" {
  source = "./modules/google/d/google_compute_health_check"

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
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the\nlast character, which cannot be a dash."
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
data "google_compute_health_check" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "check_interval_sec" {
  description = "returns a number"
  value       = data.google_compute_health_check.this.check_interval_sec
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_health_check.this.creation_timestamp
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_health_check.this.description
}

output "grpc_health_check" {
  description = "returns a list of object"
  value       = data.google_compute_health_check.this.grpc_health_check
}

output "healthy_threshold" {
  description = "returns a number"
  value       = data.google_compute_health_check.this.healthy_threshold
}

output "http2_health_check" {
  description = "returns a list of object"
  value       = data.google_compute_health_check.this.http2_health_check
}

output "http_health_check" {
  description = "returns a list of object"
  value       = data.google_compute_health_check.this.http_health_check
}

output "https_health_check" {
  description = "returns a list of object"
  value       = data.google_compute_health_check.this.https_health_check
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_health_check.this.id
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_health_check.this.self_link
}

output "ssl_health_check" {
  description = "returns a list of object"
  value       = data.google_compute_health_check.this.ssl_health_check
}

output "tcp_health_check" {
  description = "returns a list of object"
  value       = data.google_compute_health_check.this.tcp_health_check
}

output "timeout_sec" {
  description = "returns a number"
  value       = data.google_compute_health_check.this.timeout_sec
}

output "type" {
  description = "returns a string"
  value       = data.google_compute_health_check.this.type
}

output "unhealthy_threshold" {
  description = "returns a number"
  value       = data.google_compute_health_check.this.unhealthy_threshold
}

output "this" {
  value = google_compute_health_check.this
}
```

[top](#index)