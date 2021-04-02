# oci_marketplace_listing

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_marketplace_listing" {
  source = "./modules/oci/d/oci_marketplace_listing"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # listing_id - (required) is a type of string
  listing_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listing_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_marketplace_listing" "this" {
  compartment_id = var.compartment_id
  listing_id     = var.listing_id
}
```

[top](#index)

### Outputs

```terraform
output "banner" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.banner
}

output "categories" {
  description = "returns a list of string"
  value       = data.oci_marketplace_listing.this.categories
}

output "default_package_version" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.default_package_version
}

output "documentation_links" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.documentation_links
}

output "icon" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.icon
}

output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.id
}

output "is_featured" {
  description = "returns a bool"
  value       = data.oci_marketplace_listing.this.is_featured
}

output "keywords" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.keywords
}

output "languages" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.languages
}

output "license_model_description" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.license_model_description
}

output "links" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.links
}

output "listing_type" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.listing_type
}

output "long_description" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.long_description
}

output "name" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.name
}

output "package_type" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.package_type
}

output "publisher" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.publisher
}

output "regions" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.regions
}

output "release_notes" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.release_notes
}

output "screenshots" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.screenshots
}

output "short_description" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.short_description
}

output "support_contacts" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.support_contacts
}

output "support_links" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.support_links
}

output "supported_operating_systems" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.supported_operating_systems
}

output "system_requirements" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.system_requirements
}

output "tagline" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.tagline
}

output "time_released" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.time_released
}

output "usage_information" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.usage_information
}

output "version" {
  description = "returns a string"
  value       = data.oci_marketplace_listing.this.version
}

output "videos" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing.this.videos
}

output "this" {
  value = oci_marketplace_listing.this
}
```

[top](#index)