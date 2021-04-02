# oci_database_management_managed_database

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
module "oci_database_management_managed_database" {
  source = "./modules/oci/d/oci_database_management_managed_database"

  # managed_database_id - (required) is a type of string
  managed_database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_management_managed_database" "this" {
  managed_database_id = var.managed_database_id
}
```

[top](#index)

### Outputs

```terraform
output "additional_details" {
  description = "returns a map of string"
  value       = data.oci_database_management_managed_database.this.additional_details
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.compartment_id
}

output "database_status" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.database_status
}

output "database_sub_type" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.database_sub_type
}

output "database_type" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.database_type
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.id
}

output "is_cluster" {
  description = "returns a bool"
  value       = data.oci_database_management_managed_database.this.is_cluster
}

output "managed_database_groups" {
  description = "returns a list of object"
  value       = data.oci_database_management_managed_database.this.managed_database_groups
}

output "name" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.name
}

output "parent_container_id" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.parent_container_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database.this.time_created
}

output "this" {
  value = oci_database_management_managed_database.this
}
```

[top](#index)