# vcd_nsxv_dhcp_relay

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vcd_nsxv_dhcp_relay" {
  source = "./modules/vcd/d/vcd_nsxv_dhcp_relay"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name for DHCP relay settings"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxv_dhcp_relay" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "domain_names" {
  description = "returns a set of string"
  value       = data.vcd_nsxv_dhcp_relay.this.domain_names
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxv_dhcp_relay.this.id
}

output "ip_addresses" {
  description = "returns a set of string"
  value       = data.vcd_nsxv_dhcp_relay.this.ip_addresses
}

output "ip_sets" {
  description = "returns a set of string"
  value       = data.vcd_nsxv_dhcp_relay.this.ip_sets
}

output "relay_agent" {
  description = "returns a set of object"
  value       = data.vcd_nsxv_dhcp_relay.this.relay_agent
}

output "this" {
  value = vcd_nsxv_dhcp_relay.this
}
```

[top](#index)