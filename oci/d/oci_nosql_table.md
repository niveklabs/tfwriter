# oci_nosql_table

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
module "oci_nosql_table" {
  source = "./modules/oci/d/oci_nosql_table"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # table_name_or_id - (required) is a type of string
  table_name_or_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "table_name_or_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_nosql_table" "this" {
  compartment_id   = var.compartment_id
  table_name_or_id = var.table_name_or_id
}
```

[top](#index)

### Outputs

```terraform
output "ddl_statement" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.ddl_statement
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_nosql_table.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_nosql_table.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.id
}

output "is_auto_reclaimable" {
  description = "returns a bool"
  value       = data.oci_nosql_table.this.is_auto_reclaimable
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.lifecycle_details
}

output "name" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.name
}

output "schema" {
  description = "returns a list of object"
  value       = data.oci_nosql_table.this.schema
}

output "state" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_nosql_table.this.system_tags
}

output "table_limits" {
  description = "returns a list of object"
  value       = data.oci_nosql_table.this.table_limits
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.time_created
}

output "time_of_expiration" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.time_of_expiration
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_nosql_table.this.time_updated
}

output "this" {
  value = oci_nosql_table.this
}
```

[top](#index)