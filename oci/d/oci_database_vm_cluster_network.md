# oci_database_vm_cluster_network

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
module "oci_database_vm_cluster_network" {
  source = "./modules/oci/d/oci_database_vm_cluster_network"

  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = null
  # vm_cluster_network_id - (required) is a type of string
  vm_cluster_network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}

variable "vm_cluster_network_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_vm_cluster_network" "this" {
  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = var.exadata_infrastructure_id
  # vm_cluster_network_id - (required) is a type of string
  vm_cluster_network_id = var.vm_cluster_network_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_vm_cluster_network.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.display_name
}

output "dns" {
  description = "returns a list of string"
  value       = data.oci_database_vm_cluster_network.this.dns
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_vm_cluster_network.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.lifecycle_details
}

output "ntp" {
  description = "returns a list of string"
  value       = data.oci_database_vm_cluster_network.this.ntp
}

output "scans" {
  description = "returns a list of object"
  value       = data.oci_database_vm_cluster_network.this.scans
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.time_created
}

output "validate_vm_cluster_network" {
  description = "returns a bool"
  value       = data.oci_database_vm_cluster_network.this.validate_vm_cluster_network
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network.this.vm_cluster_id
}

output "vm_networks" {
  description = "returns a list of object"
  value       = data.oci_database_vm_cluster_network.this.vm_networks
}

output "this" {
  value = oci_database_vm_cluster_network.this
}
```

[top](#index)