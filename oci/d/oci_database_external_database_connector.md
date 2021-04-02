# oci_database_external_database_connector

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
module "oci_database_external_database_connector" {
  source = "./modules/oci/d/oci_database_external_database_connector"

  # external_database_connector_id - (required) is a type of string
  external_database_connector_id = null
}
```

[top](#index)

### Variables

```terraform
variable "external_database_connector_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_external_database_connector" "this" {
  external_database_connector_id = var.external_database_connector_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.compartment_id
}

output "connection_credentials" {
  description = "returns a list of object"
  value       = data.oci_database_external_database_connector.this.connection_credentials
}

output "connection_status" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.connection_status
}

output "connection_string" {
  description = "returns a list of object"
  value       = data.oci_database_external_database_connector.this.connection_string
}

output "connector_agent_id" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.connector_agent_id
}

output "connector_type" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.connector_type
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_external_database_connector.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.display_name
}

output "external_database_id" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.external_database_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_external_database_connector.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.state
}

output "time_connection_status_last_updated" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.time_connection_status_last_updated
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_external_database_connector.this.time_created
}

output "this" {
  value = oci_database_external_database_connector.this
}
```

[top](#index)