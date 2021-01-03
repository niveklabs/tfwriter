# aci_ospf_interface_policy

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_ospf_interface_policy" {
  source = "./modules/aci/d/aci_ospf_interface_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # cost - (optional) is a type of string
  cost = null
  # ctrl - (optional) is a type of string
  ctrl = null
  # dead_intvl - (optional) is a type of string
  dead_intvl = null
  # description - (optional) is a type of string
  description = null
  # hello_intvl - (optional) is a type of string
  hello_intvl = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # nw_t - (optional) is a type of string
  nw_t = null
  # pfx_suppress - (optional) is a type of string
  pfx_suppress = null
  # prio - (optional) is a type of string
  prio = null
  # rexmit_intvl - (optional) is a type of string
  rexmit_intvl = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
  # xmit_delay - (optional) is a type of string
  xmit_delay = null
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

variable "cost" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ctrl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dead_intvl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hello_intvl" {
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

variable "nw_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pfx_suppress" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rexmit_intvl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "xmit_delay" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_ospf_interface_policy" "this" {
  annotation   = var.annotation
  cost         = var.cost
  ctrl         = var.ctrl
  dead_intvl   = var.dead_intvl
  description  = var.description
  hello_intvl  = var.hello_intvl
  name         = var.name
  name_alias   = var.name_alias
  nw_t         = var.nw_t
  pfx_suppress = var.pfx_suppress
  prio         = var.prio
  rexmit_intvl = var.rexmit_intvl
  tenant_dn    = var.tenant_dn
  xmit_delay   = var.xmit_delay
}
```

[top](#index)

### Outputs

```terraform
output "cost" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.cost
}

output "ctrl" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.ctrl
}

output "dead_intvl" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.dead_intvl
}

output "description" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.description
}

output "hello_intvl" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.hello_intvl
}

output "id" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.name_alias
}

output "nw_t" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.nw_t
}

output "pfx_suppress" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.pfx_suppress
}

output "prio" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.prio
}

output "rexmit_intvl" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.rexmit_intvl
}

output "xmit_delay" {
  description = "returns a string"
  value       = data.aci_ospf_interface_policy.this.xmit_delay
}

output "this" {
  value = aci_ospf_interface_policy.this
}
```

[top](#index)