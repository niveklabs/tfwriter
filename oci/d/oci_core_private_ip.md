# oci_core_private_ip

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
module "oci_core_private_ip" {
  source = "./modules/oci/d/oci_core_private_ip"

  # private_ip_id - (required) is a type of string
  private_ip_id = null
}
```

[top](#index)

### Variables

```terraform
variable "private_ip_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_private_ip" "this" {
  private_ip_id = var.private_ip_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_private_ip.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_private_ip.this.freeform_tags
}

output "hostname_label" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.hostname_label
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.ip_address
}

output "is_primary" {
  description = "returns a bool"
  value       = data.oci_core_private_ip.this.is_primary
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.time_created
}

output "vlan_id" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.vlan_id
}

output "vnic_id" {
  description = "returns a string"
  value       = data.oci_core_private_ip.this.vnic_id
}

output "this" {
  value = oci_core_private_ip.this
}
```

[top](#index)