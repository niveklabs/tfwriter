# aci_lldp_interface_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_lldp_interface_policy" {
  source = "./modules/aci/r/aci_lldp_interface_policy"

  # admin_rx_st - (optional) is a type of string
  admin_rx_st = null
  # admin_tx_st - (optional) is a type of string
  admin_tx_st = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_rx_st" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_tx_st" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_lldp_interface_policy" "this" {
  admin_rx_st = var.admin_rx_st
  admin_tx_st = var.admin_tx_st
  annotation  = var.annotation
  description = var.description
  name        = var.name
  name_alias  = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "admin_rx_st" {
  description = "returns a string"
  value       = aci_lldp_interface_policy.this.admin_rx_st
}

output "admin_tx_st" {
  description = "returns a string"
  value       = aci_lldp_interface_policy.this.admin_tx_st
}

output "description" {
  description = "returns a string"
  value       = aci_lldp_interface_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_lldp_interface_policy.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_lldp_interface_policy.this.name_alias
}

output "this" {
  value = aci_lldp_interface_policy.this
}
```

[top](#index)