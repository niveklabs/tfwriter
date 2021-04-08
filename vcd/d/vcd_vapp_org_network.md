# vcd_vapp_org_network

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
module "vcd_vapp_org_network" {
  source = "./modules/vcd/d/vcd_vapp_org_network"

  # org - (optional) is a type of string
  org = null
  # org_network_name - (required) is a type of string
  org_network_name = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "org_network_name" {
  description = "(required) - Organization network name to which vApp network is connected to"
  type        = string
}

variable "vapp_name" {
  description = "(required) - vApp name"
  type        = string
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
data "vcd_vapp_org_network" "this" {
  # org - (optional) is a type of string
  org = var.org
  # org_network_name - (required) is a type of string
  org_network_name = var.org_network_name
  # vapp_name - (required) is a type of string
  vapp_name = var.vapp_name
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vcd_vapp_org_network.this.id
}

output "is_fenced" {
  description = "returns a bool"
  value       = data.vcd_vapp_org_network.this.is_fenced
}

output "retain_ip_mac_enabled" {
  description = "returns a bool"
  value       = data.vcd_vapp_org_network.this.retain_ip_mac_enabled
}

output "this" {
  value = vcd_vapp_org_network.this
}
```

[top](#index)