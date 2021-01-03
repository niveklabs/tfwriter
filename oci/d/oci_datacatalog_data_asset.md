# oci_datacatalog_data_asset

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
module "oci_datacatalog_data_asset" {
  source = "./modules/oci/d/oci_datacatalog_data_asset"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # data_asset_key - (required) is a type of string
  data_asset_key = null
  # fields - (optional) is a type of set of string
  fields = []
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(required)"
  type        = string
}

variable "data_asset_key" {
  description = "(required)"
  type        = string
}

variable "fields" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_datacatalog_data_asset" "this" {
  catalog_id     = var.catalog_id
  data_asset_key = var.data_asset_key
  fields         = var.fields
}
```

[top](#index)

### Outputs

```terraform
output "created_by_id" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.created_by_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.display_name
}

output "external_key" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.external_key
}

output "id" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.id
}

output "key" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.key
}

output "properties" {
  description = "returns a map of string"
  value       = data.oci_datacatalog_data_asset.this.properties
}

output "state" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.time_updated
}

output "type_key" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.type_key
}

output "updated_by_id" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.updated_by_id
}

output "uri" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_asset.this.uri
}

output "this" {
  value = oci_datacatalog_data_asset.this
}
```

[top](#index)