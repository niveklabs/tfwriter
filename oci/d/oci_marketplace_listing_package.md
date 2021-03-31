# oci_marketplace_listing_package

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_marketplace_listing_package" {
  source = "./modules/oci/d/oci_marketplace_listing_package"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # listing_id - (required) is a type of string
  listing_id = null
  # package_version - (required) is a type of string
  package_version = null
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

variable "package_version" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_marketplace_listing_package" "this" {
  compartment_id  = var.compartment_id
  listing_id      = var.listing_id
  package_version = var.package_version
}
```

[top](#index)

### Outputs

```terraform
output "app_catalog_listing_id" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.app_catalog_listing_id
}

output "app_catalog_listing_resource_version" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.app_catalog_listing_resource_version
}

output "description" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.description
}

output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.image_id
}

output "operating_system" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing_package.this.operating_system
}

output "package_type" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.package_type
}

output "pricing" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing_package.this.pricing
}

output "regions" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing_package.this.regions
}

output "resource_id" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.resource_id
}

output "resource_link" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.resource_link
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.time_created
}

output "variables" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing_package.this.variables
}

output "version" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package.this.version
}

output "this" {
  value = oci_marketplace_listing_package.this
}
```

[top](#index)