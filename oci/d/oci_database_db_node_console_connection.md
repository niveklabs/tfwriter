# oci_database_db_node_console_connection

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
module "oci_database_db_node_console_connection" {
  source = "./modules/oci/d/oci_database_db_node_console_connection"

  # db_node_id - (required) is a type of string
  db_node_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_node_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_db_node_console_connection" "this" {
  db_node_id = var.db_node_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connection.this.compartment_id
}

output "connection_string" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connection.this.connection_string
}

output "fingerprint" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connection.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connection.this.id
}

output "public_key" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connection.this.public_key
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connection.this.state
}

output "this" {
  value = oci_database_db_node_console_connection.this
}
```

[top](#index)