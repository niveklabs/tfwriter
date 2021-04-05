# ovh_iploadbalancing_vrack_network

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/ovh/d/ovh_iploadbalancing_vrack_network"

  # service_name - (required) is a type of string
  service_name = null
  # vrack_network_id - (required) is a type of number
  vrack_network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "service_name" {
  description = "(required) - The internal name of your IPloadbalancer"
  type        = string
}

variable "vrack_network_id" {
  description = "(required) - Internal Load Balancer identifier of the vRack private network"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "ovh_iploadbalancing_vrack_network" "this" {
  service_name     = var.service_name
  vrack_network_id = var.vrack_network_id
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing_vrack_network.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing_vrack_network.this.id
}

output "nat_ip" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing_vrack_network.this.nat_ip
}

output "subnet" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing_vrack_network.this.subnet
}

output "vlan" {
  description = "returns a number"
  value       = data.ovh_iploadbalancing_vrack_network.this.vlan
}

output "this" {
  value = ovh_iploadbalancing_vrack_network.this
}
```

[top](#index)