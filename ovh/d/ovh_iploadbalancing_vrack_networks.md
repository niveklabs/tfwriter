# ovh_iploadbalancing_vrack_networks

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
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_vrack_networks" {
  source = "./modules/ovh/d/ovh_iploadbalancing_vrack_networks"

  # service_name - (required) is a type of string
  service_name = null
  # subnet - (optional) is a type of string
  subnet = null
  # vlan_id - (optional) is a type of number
  vlan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "service_name" {
  description = "(required) - The internal name of your iploadbalancer."
  type        = string
}

variable "subnet" {
  description = "(optional) - Filters on subnet"
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional) - Filters on vlan id"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_iploadbalancing_vrack_networks" "this" {
  service_name = var.service_name
  subnet       = var.subnet
  vlan_id      = var.vlan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing_vrack_networks.this.id
}

output "result" {
  description = "returns a list of number"
  value       = data.ovh_iploadbalancing_vrack_networks.this.result
}

output "this" {
  value = ovh_iploadbalancing_vrack_networks.this
}
```

[top](#index)