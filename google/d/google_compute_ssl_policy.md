# google_compute_ssl_policy

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
module "google_compute_ssl_policy" {
  source = "./modules/google/d/google_compute_ssl_policy"

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
data "google_compute_ssl_policy" "this" {
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.creation_timestamp
}

output "custom_features" {
  description = "returns a set of string"
  value       = data.google_compute_ssl_policy.this.custom_features
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.description
}

output "enabled_features" {
  description = "returns a set of string"
  value       = data.google_compute_ssl_policy.this.enabled_features
}

output "fingerprint" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.id
}

output "min_tls_version" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.min_tls_version
}

output "profile" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.profile
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_ssl_policy.this.self_link
}

output "this" {
  value = google_compute_ssl_policy.this
}
```

[top](#index)