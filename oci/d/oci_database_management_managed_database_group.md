# oci_database_management_managed_database_group

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
module "oci_database_management_managed_database_group" {
  source = "./modules/oci/d/oci_database_management_managed_database_group"

  # managed_database_group_id - (required) is a type of string
  managed_database_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_database_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_management_managed_database_group" "this" {
  managed_database_group_id = var.managed_database_group_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.id
}

output "managed_databases" {
  description = "returns a list of object"
  value       = data.oci_database_management_managed_database_group.this.managed_databases
}

output "name" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_database_management_managed_database_group.this.time_updated
}

output "this" {
  value = oci_database_management_managed_database_group.this
}
```

[top](#index)