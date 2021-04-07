# oci_core_app_catalog_listing_resource_version

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
module "oci_core_app_catalog_listing_resource_version" {
  source = "./modules/oci/d/oci_core_app_catalog_listing_resource_version"

  # listing_id - (required) is a type of string
  listing_id = null
  # resource_version - (required) is a type of string
  resource_version = null
}
```

[top](#index)

### Variables

```terraform
variable "listing_id" {
  description = "(required)"
  type        = string
}

variable "resource_version" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_app_catalog_listing_resource_version" "this" {
  listing_id       = var.listing_id
  resource_version = var.resource_version
}
```

[top](#index)

### Outputs

```terraform
output "accessible_ports" {
  description = "returns a list of number"
  value       = data.oci_core_app_catalog_listing_resource_version.this.accessible_ports
}

output "allowed_actions" {
  description = "returns a list of string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.allowed_actions
}

output "available_regions" {
  description = "returns a list of string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.available_regions
}

output "compatible_shapes" {
  description = "returns a list of string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.compatible_shapes
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.id
}

output "listing_resource_id" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.listing_resource_id
}

output "listing_resource_version" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.listing_resource_version
}

output "time_published" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing_resource_version.this.time_published
}

output "this" {
  value = oci_core_app_catalog_listing_resource_version.this
}
```

[top](#index)