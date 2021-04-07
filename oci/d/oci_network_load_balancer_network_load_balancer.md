# oci_network_load_balancer_network_load_balancer

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
module "oci_network_load_balancer_network_load_balancer" {
  source = "./modules/oci/d/oci_network_load_balancer_network_load_balancer"

  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
}
```

[top](#index)

### Variables

```terraform
variable "network_load_balancer_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_network_load_balancer_network_load_balancer" "this" {
  network_load_balancer_id = var.network_load_balancer_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.id
}

output "ip_addresses" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_network_load_balancer.this.ip_addresses
}

output "is_preserve_source_destination" {
  description = "returns a bool"
  value       = data.oci_network_load_balancer_network_load_balancer.this.is_preserve_source_destination
}

output "is_private" {
  description = "returns a bool"
  value       = data.oci_network_load_balancer_network_load_balancer.this.is_private
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.lifecycle_details
}

output "network_security_group_ids" {
  description = "returns a list of string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.network_security_group_ids
}

output "reserved_ips" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_network_load_balancer.this.reserved_ips
}

output "state" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.subnet_id
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_network_load_balancer.this.time_updated
}

output "this" {
  value = oci_network_load_balancer_network_load_balancer.this
}
```

[top](#index)