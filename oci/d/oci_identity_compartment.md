# oci_identity_compartment

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
module "oci_identity_compartment" {
  source = "./modules/oci/d/oci_identity_compartment"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "oci_identity_compartment" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_compartment.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_compartment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.inactive_state
}

output "is_accessible" {
  description = "returns a bool"
  value       = data.oci_identity_compartment.this.is_accessible
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_compartment.this.time_created
}

output "this" {
  value = oci_identity_compartment.this
}
```

[top](#index)