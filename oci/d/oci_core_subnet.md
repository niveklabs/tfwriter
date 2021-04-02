# oci_core_subnet

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
module "oci_core_subnet" {
  source = "./modules/oci/d/oci_core_subnet"

  # subnet_id - (required) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "subnet_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_subnet" "this" {
  subnet_id = var.subnet_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.availability_domain
}

output "cidr_block" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.cidr_block
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_subnet.this.defined_tags
}

output "dhcp_options_id" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.dhcp_options_id
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.display_name
}

output "dns_label" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.dns_label
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_subnet.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.id
}

output "ipv6cidr_block" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.ipv6cidr_block
}

output "ipv6public_cidr_block" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.ipv6public_cidr_block
}

output "ipv6virtual_router_ip" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.ipv6virtual_router_ip
}

output "prohibit_public_ip_on_vnic" {
  description = "returns a bool"
  value       = data.oci_core_subnet.this.prohibit_public_ip_on_vnic
}

output "route_table_id" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.route_table_id
}

output "security_list_ids" {
  description = "returns a list of string"
  value       = data.oci_core_subnet.this.security_list_ids
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.state
}

output "subnet_domain_name" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.subnet_domain_name
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.time_created
}

output "vcn_id" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.vcn_id
}

output "virtual_router_ip" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.virtual_router_ip
}

output "virtual_router_mac" {
  description = "returns a string"
  value       = data.oci_core_subnet.this.virtual_router_mac
}

output "this" {
  value = oci_core_subnet.this
}
```

[top](#index)