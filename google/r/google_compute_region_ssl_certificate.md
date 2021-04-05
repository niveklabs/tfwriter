# google_compute_region_ssl_certificate

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_region_ssl_certificate" {
  source = "./modules/google/r/google_compute_region_ssl_certificate"

  # certificate - (required) is a type of string
  certificate = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # private_key - (required) is a type of string
  private_key = null
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
variable "certificate" {
  description = "(required) - The certificate in PEM format.\nThe certificate chain must be no greater than 5 certs long.\nThe chain must include at least one intermediate cert."
  type        = string
}

variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash.\n\n\nThese are in the same namespace as the managed SSL certificates."
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional) - Creates a unique name beginning with the specified prefix. Conflicts with name."
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required) - The write-only private key in PEM format."
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
resource "google_compute_region_ssl_certificate" "this" {
  certificate = var.certificate
  description = var.description
  name        = var.name
  name_prefix = var.name_prefix
  private_key = var.private_key
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
output "certificate_id" {
  description = "returns a number"
  value       = google_compute_region_ssl_certificate.this.certificate_id
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.id
}

output "name" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.name_prefix
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_region_ssl_certificate.this.self_link
}

output "this" {
  value = google_compute_region_ssl_certificate.this
}
```

[top](#index)