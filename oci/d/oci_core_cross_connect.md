# oci_core_cross_connect

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
module "oci_core_cross_connect" {
  source = "./modules/oci/d/oci_core_cross_connect"

  # cross_connect_id - (required) is a type of string
  cross_connect_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cross_connect_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_cross_connect" "this" {
  cross_connect_id = var.cross_connect_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.compartment_id
}

output "cross_connect_group_id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.cross_connect_group_id
}

output "customer_reference_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.customer_reference_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_cross_connect.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.display_name
}

output "far_cross_connect_or_cross_connect_group_id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.far_cross_connect_or_cross_connect_group_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_cross_connect.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.id
}

output "is_active" {
  description = "returns a bool"
  value       = data.oci_core_cross_connect.this.is_active
}

output "location_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.location_name
}

output "near_cross_connect_or_cross_connect_group_id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.near_cross_connect_or_cross_connect_group_id
}

output "port_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.port_name
}

output "port_speed_shape_name" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.port_speed_shape_name
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_cross_connect.this.time_created
}

output "this" {
  value = oci_core_cross_connect.this
}
```

[top](#index)