# oci_core_vlan

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
module "oci_core_vlan" {
  source = "./modules/oci/d/oci_core_vlan"

  # vlan_id - (required) is a type of string
  vlan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "vlan_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_vlan" "this" {
  # vlan_id - (required) is a type of string
  vlan_id = var.vlan_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.availability_domain
}

output "cidr_block" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.cidr_block
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_vlan.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_vlan.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.id
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_core_vlan.this.nsg_ids
}

output "route_table_id" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.route_table_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.time_created
}

output "vcn_id" {
  description = "returns a string"
  value       = data.oci_core_vlan.this.vcn_id
}

output "vlan_tag" {
  description = "returns a number"
  value       = data.oci_core_vlan.this.vlan_tag
}

output "this" {
  value = oci_core_vlan.this
}
```

[top](#index)