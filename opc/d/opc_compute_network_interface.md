# opc_compute_network_interface

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_network_interface" {
  source = "./modules/opc/d/opc_compute_network_interface"

  # instance_id - (required) is a type of string
  instance_id = null
  # instance_name - (required) is a type of string
  instance_name = null
  # interface - (required) is a type of string
  interface = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "interface" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opc_compute_network_interface" "this" {
  instance_id   = var.instance_id
  instance_name = var.instance_name
  interface     = var.interface
}
```

[top](#index)

### Outputs

```terraform
output "dns" {
  description = "returns a list of string"
  value       = data.opc_compute_network_interface.this.dns
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_network_interface.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.opc_compute_network_interface.this.ip_address
}

output "ip_network" {
  description = "returns a string"
  value       = data.opc_compute_network_interface.this.ip_network
}

output "is_default_gateway" {
  description = "returns a bool"
  value       = data.opc_compute_network_interface.this.is_default_gateway
}

output "mac_address" {
  description = "returns a string"
  value       = data.opc_compute_network_interface.this.mac_address
}

output "model" {
  description = "returns a string"
  value       = data.opc_compute_network_interface.this.model
}

output "name_servers" {
  description = "returns a list of string"
  value       = data.opc_compute_network_interface.this.name_servers
}

output "nat" {
  description = "returns a list of string"
  value       = data.opc_compute_network_interface.this.nat
}

output "search_domains" {
  description = "returns a list of string"
  value       = data.opc_compute_network_interface.this.search_domains
}

output "sec_lists" {
  description = "returns a list of string"
  value       = data.opc_compute_network_interface.this.sec_lists
}

output "shared_network" {
  description = "returns a bool"
  value       = data.opc_compute_network_interface.this.shared_network
}

output "vnic" {
  description = "returns a string"
  value       = data.opc_compute_network_interface.this.vnic
}

output "vnic_sets" {
  description = "returns a list of string"
  value       = data.opc_compute_network_interface.this.vnic_sets
}

output "this" {
  value = opc_compute_network_interface.this
}
```

[top](#index)