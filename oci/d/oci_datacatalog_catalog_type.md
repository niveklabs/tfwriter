# oci_datacatalog_catalog_type

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datacatalog_catalog_type" {
  source = "./modules/oci/d/oci_datacatalog_catalog_type"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # fields - (optional) is a type of set of string
  fields = []
  # type_key - (required) is a type of string
  type_key = null
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(required)"
  type        = string
}

variable "fields" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "type_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_datacatalog_catalog_type" "this" {
  catalog_id = var.catalog_id
  fields     = var.fields
  type_key   = var.type_key
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.description
}

output "external_type_name" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.external_type_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.id
}

output "is_approved" {
  description = "returns a bool"
  value       = data.oci_datacatalog_catalog_type.this.is_approved
}

output "is_internal" {
  description = "returns a bool"
  value       = data.oci_datacatalog_catalog_type.this.is_internal
}

output "is_tag" {
  description = "returns a bool"
  value       = data.oci_datacatalog_catalog_type.this.is_tag
}

output "key" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.key
}

output "name" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.name
}

output "properties" {
  description = "returns a map of string"
  value       = data.oci_datacatalog_catalog_type.this.properties
}

output "state" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.state
}

output "type_category" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.type_category
}

output "uri" {
  description = "returns a string"
  value       = data.oci_datacatalog_catalog_type.this.uri
}

output "this" {
  value = oci_datacatalog_catalog_type.this
}
```

[top](#index)