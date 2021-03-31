# oci_identity_group

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
module "oci_identity_group" {
  source = "./modules/oci/d/oci_identity_group"

  # group_id - (required) is a type of string
  group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_group" "this" {
  group_id = var.group_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_identity_group.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_group.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_identity_group.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_group.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = data.oci_identity_group.this.inactive_state
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_group.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_group.this.time_created
}

output "this" {
  value = oci_identity_group.this
}
```

[top](#index)