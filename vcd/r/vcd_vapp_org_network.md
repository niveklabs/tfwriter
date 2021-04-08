# vcd_vapp_org_network

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
module "vcd_vapp_org_network" {
  source = "./modules/vcd/r/vcd_vapp_org_network"

  # is_fenced - (optional) is a type of bool
  is_fenced = null
  # org - (optional) is a type of string
  org = null
  # org_network_name - (required) is a type of string
  org_network_name = null
  # retain_ip_mac_enabled - (optional) is a type of bool
  retain_ip_mac_enabled = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "is_fenced" {
  description = "(optional) - Fencing allows identical virtual machines in different vApp networks connect to organization VDC networks that are accessed in this vApp"
  type        = bool
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "org_network_name" {
  description = "(required) - Organization network name to which vApp network is connected to"
  type        = string
}

variable "retain_ip_mac_enabled" {
  description = "(optional) - Specifies whether the network resources such as IP/MAC of router will be retained across deployments. Default is false."
  type        = bool
  default     = null
}

variable "vapp_name" {
  description = "(required) - vApp network name"
  type        = string
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
resource "vcd_vapp_org_network" "this" {
  # is_fenced - (optional) is a type of bool
  is_fenced = var.is_fenced
  # org - (optional) is a type of string
  org = var.org
  # org_network_name - (required) is a type of string
  org_network_name = var.org_network_name
  # retain_ip_mac_enabled - (optional) is a type of bool
  retain_ip_mac_enabled = var.retain_ip_mac_enabled
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
  value       = vcd_vapp_org_network.this.id
}

output "this" {
  value = vcd_vapp_org_network.this
}
```

[top](#index)