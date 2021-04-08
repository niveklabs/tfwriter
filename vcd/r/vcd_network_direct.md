# vcd_network_direct

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_network_direct" {
  source = "./modules/vcd/r/vcd_network_direct"

  # description - (optional) is a type of string
  description = null
  # external_network - (required) is a type of string
  external_network = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # shared - (optional) is a type of bool
  shared = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Optional description for the network"
  type        = string
  default     = null
}

variable "external_network" {
  description = "(required) - The name of the external network"
  type        = string
}

variable "name" {
  description = "(required) - A unique name for this network"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "shared" {
  description = "(optional) - Defines if this network is shared between multiple VDCs in the Org"
  type        = bool
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_network_direct" "this" {
  # description - (optional) is a type of string
  description = var.description
  # external_network - (required) is a type of string
  external_network = var.external_network
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # shared - (optional) is a type of bool
  shared = var.shared
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "external_network_dns1" {
  description = "returns a string"
  value       = vcd_network_direct.this.external_network_dns1
}

output "external_network_dns2" {
  description = "returns a string"
  value       = vcd_network_direct.this.external_network_dns2
}

output "external_network_dns_suffix" {
  description = "returns a string"
  value       = vcd_network_direct.this.external_network_dns_suffix
}

output "external_network_gateway" {
  description = "returns a string"
  value       = vcd_network_direct.this.external_network_gateway
}

output "external_network_netmask" {
  description = "returns a string"
  value       = vcd_network_direct.this.external_network_netmask
}

output "href" {
  description = "returns a string"
  value       = vcd_network_direct.this.href
}

output "id" {
  description = "returns a string"
  value       = vcd_network_direct.this.id
}

output "this" {
  value = vcd_network_direct.this
}
```

[top](#index)