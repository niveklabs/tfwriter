# oci_core_nat_gateway

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
module "oci_core_nat_gateway" {
  source = "./modules/oci/d/oci_core_nat_gateway"

  # nat_gateway_id - (required) is a type of string
  nat_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "nat_gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_nat_gateway" "this" {
  # nat_gateway_id - (required) is a type of string
  nat_gateway_id = var.nat_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "block_traffic" {
  description = "returns a bool"
  value       = data.oci_core_nat_gateway.this.block_traffic
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_nat_gateway.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_nat_gateway.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.id
}

output "nat_ip" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.nat_ip
}

output "public_ip_id" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.public_ip_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.time_created
}

output "vcn_id" {
  description = "returns a string"
  value       = data.oci_core_nat_gateway.this.vcn_id
}

output "this" {
  value = oci_core_nat_gateway.this
}
```

[top](#index)