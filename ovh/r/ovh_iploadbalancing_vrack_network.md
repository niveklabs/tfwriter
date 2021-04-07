# ovh_iploadbalancing_vrack_network

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_vrack_network" {
  source = "./modules/ovh/r/ovh_iploadbalancing_vrack_network"

  # display_name - (optional) is a type of string
  display_name = null
  # farm_id - (optional) is a type of list of number
  farm_id = []
  # nat_ip - (required) is a type of string
  nat_ip = null
  # service_name - (required) is a type of string
  service_name = null
  # subnet - (required) is a type of string
  subnet = null
  # vlan - (optional) is a type of number
  vlan = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional) - Human readable name for your vrack network"
  type        = string
  default     = null
}

variable "farm_id" {
  description = "(optional) - This attribute is there for documentation purpose only and isnt passed to the OVH API as it may conflicts with http/tcp farms `vrack_network_id` attribute"
  type        = list(number)
  default     = null
}

variable "nat_ip" {
  description = "(required) - An IP block used as a pool of IPs by this Load Balancer to connect to the servers in this private network. The blck must be in the private network and reserved for the Load Balancer"
  type        = string
}

variable "service_name" {
  description = "(required) - The internal name of your IPloadbalancer"
  type        = string
}

variable "subnet" {
  description = "(required) - IP block of the private network in the vRack"
  type        = string
}

variable "vlan" {
  description = "(optional) - VLAN of the private network in the vRack. 0 if the private network is not in a VLAN"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_vrack_network" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # farm_id - (optional) is a type of list of number
  farm_id = var.farm_id
  # nat_ip - (required) is a type of string
  nat_ip = var.nat_ip
  # service_name - (required) is a type of string
  service_name = var.service_name
  # subnet - (required) is a type of string
  subnet = var.subnet
  # vlan - (optional) is a type of number
  vlan = var.vlan
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_vrack_network.this.id
}

output "vlan" {
  description = "returns a number"
  value       = ovh_iploadbalancing_vrack_network.this.vlan
}

output "vrack_network_id" {
  description = "returns a number"
  value       = ovh_iploadbalancing_vrack_network.this.vrack_network_id
}

output "this" {
  value = ovh_iploadbalancing_vrack_network.this
}
```

[top](#index)