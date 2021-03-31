# oci_datacatalog_catalog

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
module "oci_datacatalog_catalog" {
  source = "./modules/oci/d/oci_datacatalog_catalog"

  # catalog_id - (required) is a type of string
  catalog_id = null
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_datacatalog_catalog" "this" {
  catalog_id = var.catalog_id
}
```

[top](#index)

### Outputs

```terraform
output "attached_catalog_private_endpoints" {
  description = "returns a list of string"
  value       = data.oci_datacatalog_catalog.this.attached_catalog_private_endpoints
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_datacatalog_catalog.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_datacatalog_catalog.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.lifecycle_details
}

output "number_of_objects" {
  description = "returns a number"
  value       = data.oci_datacatalog_catalog.this.number_of_objects
}

output "service_api_url" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.service_api_url
}

output "service_console_url" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.service_console_url
}

output "state" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog.this.time_updated
}

output "this" {
  value = oci_datacatalog_catalog.this
}
```

[top](#index)