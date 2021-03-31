# aci_interface_fc_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aci_interface_fc_policy" {
  source = "./modules/aci/d/aci_interface_fc_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # automaxspeed - (optional) is a type of string
  automaxspeed = null
  # description - (optional) is a type of string
  description = null
  # fill_pattern - (optional) is a type of string
  fill_pattern = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # port_mode - (optional) is a type of string
  port_mode = null
  # rx_bb_credit - (optional) is a type of string
  rx_bb_credit = null
  # speed - (optional) is a type of string
  speed = null
  # trunk_mode - (optional) is a type of string
  trunk_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "automaxspeed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fill_pattern" {
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

variable "port_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rx_bb_credit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "speed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trunk_mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_interface_fc_policy" "this" {
  annotation   = var.annotation
  automaxspeed = var.automaxspeed
  description  = var.description
  fill_pattern = var.fill_pattern
  name         = var.name
  name_alias   = var.name_alias
  port_mode    = var.port_mode
  rx_bb_credit = var.rx_bb_credit
  speed        = var.speed
  trunk_mode   = var.trunk_mode
}
```

[top](#index)

### Outputs

```terraform
output "automaxspeed" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.automaxspeed
}

output "description" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.description
}

output "fill_pattern" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.fill_pattern
}

output "id" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.name_alias
}

output "port_mode" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.port_mode
}

output "rx_bb_credit" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.rx_bb_credit
}

output "speed" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.speed
}

output "trunk_mode" {
  description = "returns a string"
  value       = data.aci_interface_fc_policy.this.trunk_mode
}

output "this" {
  value = aci_interface_fc_policy.this
}
```

[top](#index)