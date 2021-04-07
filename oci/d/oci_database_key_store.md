# oci_database_key_store

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
module "oci_database_key_store" {
  source = "./modules/oci/d/oci_database_key_store"

  # key_store_id - (required) is a type of string
  key_store_id = null
}
```

[top](#index)

### Variables

```terraform
variable "key_store_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_key_store" "this" {
  # key_store_id - (required) is a type of string
  key_store_id = var.key_store_id
}
```

[top](#index)

### Outputs

```terraform
output "associated_databases" {
  description = "returns a list of object"
  value       = data.oci_database_key_store.this.associated_databases
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_key_store.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_key_store.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_key_store.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_key_store.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_key_store.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_key_store.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_key_store.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_key_store.this.time_created
}

output "type_details" {
  description = "returns a list of object"
  value       = data.oci_database_key_store.this.type_details
}

output "this" {
  value = oci_database_key_store.this
}
```

[top](#index)