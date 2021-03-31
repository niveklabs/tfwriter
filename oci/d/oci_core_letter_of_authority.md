# oci_core_letter_of_authority

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
module "oci_core_letter_of_authority" {
  source = "./modules/oci/d/oci_core_letter_of_authority"

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
data "oci_core_letter_of_authority" "this" {
  cross_connect_id = var.cross_connect_id
}
```

[top](#index)

### Outputs

```terraform
output "authorized_entity_name" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.authorized_entity_name
}

output "circuit_type" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.circuit_type
}

output "facility_location" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.facility_location
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.id
}

output "port_name" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.port_name
}

output "time_expires" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.time_expires
}

output "time_issued" {
  description = "returns a string"
  value       = data.oci_core_letter_of_authority.this.time_issued
}

output "this" {
  value = oci_core_letter_of_authority.this
}
```

[top](#index)