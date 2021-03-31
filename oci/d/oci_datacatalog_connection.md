# oci_datacatalog_connection

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
module "oci_datacatalog_connection" {
  source = "./modules/oci/d/oci_datacatalog_connection"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # connection_key - (required) is a type of string
  connection_key = null
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

variable "connection_key" {
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
data "oci_datacatalog_connection" "this" {
  catalog_id     = var.catalog_id
  connection_key = var.connection_key
  data_asset_key = var.data_asset_key
  fields         = var.fields
}
```

[top](#index)

### Outputs

```terraform
output "created_by_id" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.created_by_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.display_name
}

output "enc_properties" {
  description = "returns a map of string"
  value       = data.oci_datacatalog_connection.this.enc_properties
  sensitive   = true
}

output "external_key" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.external_key
}

output "id" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = data.oci_datacatalog_connection.this.is_default
}

output "key" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.key
}

output "properties" {
  description = "returns a map of string"
  value       = data.oci_datacatalog_connection.this.properties
}

output "state" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.time_created
}

output "time_status_updated" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.time_status_updated
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.time_updated
}

output "type_key" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.type_key
}

output "updated_by_id" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.updated_by_id
}

output "uri" {
  description = "returns a string"
  value       = data.oci_datacatalog_connection.this.uri
}

output "this" {
  value = oci_datacatalog_connection.this
}
```

[top](#index)