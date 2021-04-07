# triton_fabric

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "triton_fabric" {
  source = "./modules/triton/r/triton_fabric"

  # description - (optional) is a type of string
  description = null
  # gateway - (optional) is a type of string
  gateway = null
  # internet_nat - (optional) is a type of bool
  internet_nat = null
  # name - (required) is a type of string
  name = null
  # provision_end_ip - (required) is a type of string
  provision_end_ip = null
  # provision_start_ip - (required) is a type of string
  provision_start_ip = null
  # resolvers - (optional) is a type of list of string
  resolvers = []
  # routes - (optional) is a type of map of string
  routes = {}
  # subnet - (required) is a type of string
  subnet = null
  # vlan_id - (required) is a type of number
  vlan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of network"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(optional) - Gateway IP"
  type        = string
  default     = null
}

variable "internet_nat" {
  description = "(optional) - Whether or not a NAT zone is provisioned at the Gateway IP address"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Network name"
  type        = string
}

variable "provision_end_ip" {
  description = "(required) - Last assignable IP on the network"
  type        = string
}

variable "provision_start_ip" {
  description = "(required) - First IP on the network that can be assigned"
  type        = string
}

variable "resolvers" {
  description = "(optional) - List of IP addresses for DNS resolvers"
  type        = list(string)
  default     = null
}

variable "routes" {
  description = "(optional) - Map of CIDR block to Gateway IP address"
  type        = map(string)
  default     = null
}

variable "subnet" {
  description = "(required) - CIDR formatted string describing network address space"
  type        = string
}

variable "vlan_id" {
  description = "(required) - VLAN on which the network exists"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "triton_fabric" "this" {
  # description - (optional) is a type of string
  description = var.description
  # gateway - (optional) is a type of string
  gateway = var.gateway
  # internet_nat - (optional) is a type of bool
  internet_nat = var.internet_nat
  # name - (required) is a type of string
  name = var.name
  # provision_end_ip - (required) is a type of string
  provision_end_ip = var.provision_end_ip
  # provision_start_ip - (required) is a type of string
  provision_start_ip = var.provision_start_ip
  # resolvers - (optional) is a type of list of string
  resolvers = var.resolvers
  # routes - (optional) is a type of map of string
  routes = var.routes
  # subnet - (required) is a type of string
  subnet = var.subnet
  # vlan_id - (required) is a type of number
  vlan_id = var.vlan_id
}
```

[top](#index)

### Outputs

```terraform
output "fabric" {
  description = "returns a bool"
  value       = triton_fabric.this.fabric
}

output "id" {
  description = "returns a string"
  value       = triton_fabric.this.id
}

output "public" {
  description = "returns a bool"
  value       = triton_fabric.this.public
}

output "resolvers" {
  description = "returns a list of string"
  value       = triton_fabric.this.resolvers
}

output "routes" {
  description = "returns a map of string"
  value       = triton_fabric.this.routes
}

output "this" {
  value = triton_fabric.this
}
```

[top](#index)