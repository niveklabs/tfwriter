# aci_subnet

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
module "aci_subnet" {
  source = "./modules/aci/r/aci_subnet"

  # annotation - (optional) is a type of string
  annotation = null
  # ctrl - (optional) is a type of list of string
  ctrl = []
  # description - (optional) is a type of string
  description = null
  # ip - (required) is a type of string
  ip = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # parent_dn - (required) is a type of string
  parent_dn = null
  # preferred - (optional) is a type of string
  preferred = null
  # relation_fv_rs_bd_subnet_to_out - (optional) is a type of set of string
  relation_fv_rs_bd_subnet_to_out = []
  # relation_fv_rs_bd_subnet_to_profile - (optional) is a type of string
  relation_fv_rs_bd_subnet_to_profile = null
  # relation_fv_rs_nd_pfx_pol - (optional) is a type of string
  relation_fv_rs_nd_pfx_pol = null
  # scope - (optional) is a type of list of string
  scope = []
  # virtual - (optional) is a type of string
  virtual = null
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

variable "ctrl" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_dn" {
  description = "(required)"
  type        = string
}

variable "preferred" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_subnet_to_out" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_bd_subnet_to_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_nd_pfx_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "virtual" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_subnet" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # ctrl - (optional) is a type of list of string
  ctrl = var.ctrl
  # description - (optional) is a type of string
  description = var.description
  # ip - (required) is a type of string
  ip = var.ip
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # parent_dn - (required) is a type of string
  parent_dn = var.parent_dn
  # preferred - (optional) is a type of string
  preferred = var.preferred
  # relation_fv_rs_bd_subnet_to_out - (optional) is a type of set of string
  relation_fv_rs_bd_subnet_to_out = var.relation_fv_rs_bd_subnet_to_out
  # relation_fv_rs_bd_subnet_to_profile - (optional) is a type of string
  relation_fv_rs_bd_subnet_to_profile = var.relation_fv_rs_bd_subnet_to_profile
  # relation_fv_rs_nd_pfx_pol - (optional) is a type of string
  relation_fv_rs_nd_pfx_pol = var.relation_fv_rs_nd_pfx_pol
  # scope - (optional) is a type of list of string
  scope = var.scope
  # virtual - (optional) is a type of string
  virtual = var.virtual
}
```

[top](#index)

### Outputs

```terraform
output "ctrl" {
  description = "returns a list of string"
  value       = aci_subnet.this.ctrl
}

output "description" {
  description = "returns a string"
  value       = aci_subnet.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_subnet.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_subnet.this.name_alias
}

output "preferred" {
  description = "returns a string"
  value       = aci_subnet.this.preferred
}

output "scope" {
  description = "returns a list of string"
  value       = aci_subnet.this.scope
}

output "virtual" {
  description = "returns a string"
  value       = aci_subnet.this.virtual
}

output "this" {
  value = aci_subnet.this
}
```

[top](#index)