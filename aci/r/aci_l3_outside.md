# aci_l3_outside

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_l3_outside" {
  source = "./modules/aci/r/aci_l3_outside"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # enforce_rtctrl - (optional) is a type of string
  enforce_rtctrl = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_l3ext_rs_ectx - (optional) is a type of string
  relation_l3ext_rs_ectx = null
  # relation_l3ext_rs_interleak_pol - (optional) is a type of string
  relation_l3ext_rs_interleak_pol = null
  # relation_l3ext_rs_l3_dom_att - (optional) is a type of string
  relation_l3ext_rs_l3_dom_att = null
  # relation_l3ext_rs_out_to_bd_public_subnet_holder - (optional) is a type of set of string
  relation_l3ext_rs_out_to_bd_public_subnet_holder = []
  # target_dscp - (optional) is a type of string
  target_dscp = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null

  relation_l3ext_rs_dampening_pol = [{
    af                     = null
    tn_rtctrl_profile_name = null
  }]
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enforce_rtctrl" {
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

variable "relation_l3ext_rs_ectx" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_interleak_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_l3_dom_att" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_out_to_bd_public_subnet_holder" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "target_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "relation_l3ext_rs_dampening_pol" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      af                     = string
      tn_rtctrl_profile_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aci_l3_outside" "this" {
  annotation                                       = var.annotation
  description                                      = var.description
  enforce_rtctrl                                   = var.enforce_rtctrl
  name                                             = var.name
  name_alias                                       = var.name_alias
  relation_l3ext_rs_ectx                           = var.relation_l3ext_rs_ectx
  relation_l3ext_rs_interleak_pol                  = var.relation_l3ext_rs_interleak_pol
  relation_l3ext_rs_l3_dom_att                     = var.relation_l3ext_rs_l3_dom_att
  relation_l3ext_rs_out_to_bd_public_subnet_holder = var.relation_l3ext_rs_out_to_bd_public_subnet_holder
  target_dscp                                      = var.target_dscp
  tenant_dn                                        = var.tenant_dn

  dynamic "relation_l3ext_rs_dampening_pol" {
    for_each = var.relation_l3ext_rs_dampening_pol
    content {
      af                     = relation_l3ext_rs_dampening_pol.value["af"]
      tn_rtctrl_profile_name = relation_l3ext_rs_dampening_pol.value["tn_rtctrl_profile_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_l3_outside.this.description
}

output "enforce_rtctrl" {
  description = "returns a string"
  value       = aci_l3_outside.this.enforce_rtctrl
}

output "id" {
  description = "returns a string"
  value       = aci_l3_outside.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_l3_outside.this.name_alias
}

output "target_dscp" {
  description = "returns a string"
  value       = aci_l3_outside.this.target_dscp
}

output "this" {
  value = aci_l3_outside.this
}
```

[top](#index)