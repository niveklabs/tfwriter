# oci_nosql_index

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
module "oci_nosql_index" {
  source = "./modules/oci/d/oci_nosql_index"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # index_name - (required) is a type of string
  index_name = null
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

variable "index_name" {
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
data "oci_nosql_index" "this" {
  compartment_id   = var.compartment_id
  index_name       = var.index_name
  table_name_or_id = var.table_name_or_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_nosql_index.this.id
}

output "is_if_not_exists" {
  description = "returns a bool"
  value       = data.oci_nosql_index.this.is_if_not_exists
}

output "keys" {
  description = "returns a list of object"
  value       = data.oci_nosql_index.this.keys
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_nosql_index.this.lifecycle_details
}

output "name" {
  description = "returns a string"
  value       = data.oci_nosql_index.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_nosql_index.this.state
}

output "table_id" {
  description = "returns a string"
  value       = data.oci_nosql_index.this.table_id
}

output "table_name" {
  description = "returns a string"
  value       = data.oci_nosql_index.this.table_name
}

output "this" {
  value = oci_nosql_index.this
}
```

[top](#index)