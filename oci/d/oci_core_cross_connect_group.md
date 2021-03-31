# oci_core_cross_connect_group

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
module "oci_core_cross_connect_group" {
  source = "./modules/oci/d/oci_core_cross_connect_group"

  # cross_connect_group_id - (required) is a type of string
  cross_connect_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cross_connect_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_cross_connect_group" "this" {
  cross_connect_group_id = var.cross_connect_group_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_group.this.compartment_id
}

output "customer_reference_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_group.this.customer_reference_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_cross_connect_group.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_group.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_cross_connect_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_group.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_group.this.time_created
}

output "this" {
  value = oci_core_cross_connect_group.this
}
```

[top](#index)