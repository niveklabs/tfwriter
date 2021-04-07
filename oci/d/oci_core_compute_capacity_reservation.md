# oci_core_compute_capacity_reservation

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_compute_capacity_reservation" {
  source = "./modules/oci/d/oci_core_compute_capacity_reservation"

  # capacity_reservation_id - (required) is a type of string
  capacity_reservation_id = null
}
```

[top](#index)

### Variables

```terraform
variable "capacity_reservation_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_compute_capacity_reservation" "this" {
  capacity_reservation_id = var.capacity_reservation_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_compute_capacity_reservation.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_compute_capacity_reservation.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.id
}

output "instance_reservation_configs" {
  description = "returns a list of object"
  value       = data.oci_core_compute_capacity_reservation.this.instance_reservation_configs
}

output "is_default_reservation" {
  description = "returns a bool"
  value       = data.oci_core_compute_capacity_reservation.this.is_default_reservation
}

output "reserved_instance_count" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.reserved_instance_count
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.time_updated
}

output "used_instance_count" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation.this.used_instance_count
}

output "this" {
  value = oci_core_compute_capacity_reservation.this
}
```

[top](#index)