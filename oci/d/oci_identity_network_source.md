# oci_identity_network_source

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
module "oci_identity_network_source" {
  source = "./modules/oci/d/oci_identity_network_source"

  # network_source_id - (required) is a type of string
  network_source_id = null
}
```

[top](#index)

### Variables

```terraform
variable "network_source_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_network_source" "this" {
  network_source_id = var.network_source_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_network_source.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_network_source.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.inactive_state
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.name
}

output "public_source_list" {
  description = "returns a list of string"
  value       = data.oci_identity_network_source.this.public_source_list
}

output "services" {
  description = "returns a list of string"
  value       = data.oci_identity_network_source.this.services
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_network_source.this.time_created
}

output "virtual_source_list" {
  description = "returns a list of object"
  value       = data.oci_identity_network_source.this.virtual_source_list
}

output "this" {
  value = oci_identity_network_source.this
}
```

[top](#index)