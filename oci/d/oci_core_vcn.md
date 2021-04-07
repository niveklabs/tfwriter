# oci_core_vcn

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
module "oci_core_vcn" {
  source = "./modules/oci/d/oci_core_vcn"

  # vcn_id - (required) is a type of string
  vcn_id = null
}
```

[top](#index)

### Variables

```terraform
variable "vcn_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_vcn" "this" {
  vcn_id = var.vcn_id
}
```

[top](#index)

### Outputs

```terraform
output "cidr_block" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.cidr_block
}

output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.oci_core_vcn.this.cidr_blocks
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.compartment_id
}

output "default_dhcp_options_id" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.default_dhcp_options_id
}

output "default_route_table_id" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.default_route_table_id
}

output "default_security_list_id" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.default_security_list_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_vcn.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.display_name
}

output "dns_label" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.dns_label
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_vcn.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.id
}

output "ipv6cidr_block" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.ipv6cidr_block
}

output "ipv6public_cidr_block" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.ipv6public_cidr_block
}

output "is_ipv6enabled" {
  description = "returns a bool"
  value       = data.oci_core_vcn.this.is_ipv6enabled
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.time_created
}

output "vcn_domain_name" {
  description = "returns a string"
  value       = data.oci_core_vcn.this.vcn_domain_name
}

output "this" {
  value = oci_core_vcn.this
}
```

[top](#index)