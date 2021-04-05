# triton_fabric_network

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_fabric_network" {
  source = "./modules/triton/d/triton_fabric_network"

  # name - (required) is a type of string
  name = null
  # vlan_id - (required) is a type of number
  vlan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "vlan_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "triton_fabric_network" "this" {
  name    = var.name
  vlan_id = var.vlan_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.triton_fabric_network.this.description
}

output "fabric" {
  description = "returns a bool"
  value       = data.triton_fabric_network.this.fabric
}

output "gateway" {
  description = "returns a string"
  value       = data.triton_fabric_network.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.triton_fabric_network.this.id
}

output "internet_nat" {
  description = "returns a bool"
  value       = data.triton_fabric_network.this.internet_nat
}

output "provision_end_ip" {
  description = "returns a string"
  value       = data.triton_fabric_network.this.provision_end_ip
}

output "provision_start_ip" {
  description = "returns a string"
  value       = data.triton_fabric_network.this.provision_start_ip
}

output "public" {
  description = "returns a bool"
  value       = data.triton_fabric_network.this.public
}

output "resolvers" {
  description = "returns a list of string"
  value       = data.triton_fabric_network.this.resolvers
}

output "routes" {
  description = "returns a map of string"
  value       = data.triton_fabric_network.this.routes
}

output "subnet" {
  description = "returns a string"
  value       = data.triton_fabric_network.this.subnet
}

output "this" {
  value = triton_fabric_network.this
}
```

[top](#index)