# google_compute_region_ssl_certificate

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
module "google_compute_region_ssl_certificate" {
  source = "./modules/google-beta/d/google_compute_region_ssl_certificate"

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
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash.\n\n\nThese are in the same namespace as the managed SSL certificates."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the created regional ssl certificate should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_region_ssl_certificate" "this" {
  name    = var.name
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.certificate
}

output "certificate_id" {
  description = "returns a number"
  value       = data.google_compute_region_ssl_certificate.this.certificate_id
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.creation_timestamp
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.id
}

output "name_prefix" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.name_prefix
}

output "private_key" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.private_key
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_region_ssl_certificate.this.self_link
}

output "this" {
  value = google_compute_region_ssl_certificate.this
}
```

[top](#index)