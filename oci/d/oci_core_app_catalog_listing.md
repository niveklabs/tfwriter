# oci_core_app_catalog_listing

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_app_catalog_listing" {
  source = "./modules/oci/d/oci_core_app_catalog_listing"

  # listing_id - (required) is a type of string
  listing_id = null
}
```

[top](#index)

### Variables

```terraform
variable "listing_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_app_catalog_listing" "this" {
  listing_id = var.listing_id
}
```

[top](#index)

### Outputs

```terraform
output "contact_url" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.contact_url
}

output "description" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.id
}

output "publisher_logo_url" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.publisher_logo_url
}

output "publisher_name" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.publisher_name
}

output "summary" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.summary
}

output "time_published" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing.this.time_published
}

output "this" {
  value = oci_core_app_catalog_listing.this
}
```

[top](#index)