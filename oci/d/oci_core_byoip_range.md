# oci_core_byoip_range

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
module "oci_core_byoip_range" {
  source = "./modules/oci/d/oci_core_byoip_range"

  # byoip_range_id - (required) is a type of string
  byoip_range_id = null
}
```

[top](#index)

### Variables

```terraform
variable "byoip_range_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_byoip_range" "this" {
  byoip_range_id = var.byoip_range_id
}
```

[top](#index)

### Outputs

```terraform
output "cidr_block" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.cidr_block
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_byoip_range.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_byoip_range.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.state
}

output "time_advertised" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.time_advertised
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.time_created
}

output "time_validated" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.time_validated
}

output "time_withdrawn" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.time_withdrawn
}

output "validation_token" {
  description = "returns a string"
  value       = data.oci_core_byoip_range.this.validation_token
}

output "this" {
  value = oci_core_byoip_range.this
}
```

[top](#index)