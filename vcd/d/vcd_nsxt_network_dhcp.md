# vcd_nsxt_network_dhcp

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
module "vcd_nsxt_network_dhcp" {
  source = "./modules/vcd/d/vcd_nsxt_network_dhcp"

  # org - (optional) is a type of string
  org = null
  # org_network_id - (required) is a type of string
  org_network_id = null
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

variable "org_network_id" {
  description = "(required) - Parent Org VDC network name"
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
data "vcd_nsxt_network_dhcp" "this" {
  # org - (optional) is a type of string
  org = var.org
  # org_network_id - (required) is a type of string
  org_network_id = var.org_network_id
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vcd_nsxt_network_dhcp.this.id
}

output "pool" {
  description = "returns a set of object"
  value       = data.vcd_nsxt_network_dhcp.this.pool
}

output "this" {
  value = vcd_nsxt_network_dhcp.this
}
```

[top](#index)