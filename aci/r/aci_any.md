# aci_any

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
module "aci_any" {
  source = "./modules/aci/r/aci_any"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # match_t - (optional) is a type of string
  match_t = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pref_gr_memb - (optional) is a type of string
  pref_gr_memb = null
  # relation_vz_rs_any_to_cons - (optional) is a type of set of string
  relation_vz_rs_any_to_cons = []
  # relation_vz_rs_any_to_cons_if - (optional) is a type of set of string
  relation_vz_rs_any_to_cons_if = []
  # relation_vz_rs_any_to_prov - (optional) is a type of set of string
  relation_vz_rs_any_to_prov = []
  # vrf_dn - (required) is a type of string
  vrf_dn = null
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

variable "match_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pref_gr_memb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vz_rs_any_to_cons" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_vz_rs_any_to_cons_if" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_vz_rs_any_to_prov" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "vrf_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_any" "this" {
  annotation                    = var.annotation
  description                   = var.description
  match_t                       = var.match_t
  name_alias                    = var.name_alias
  pref_gr_memb                  = var.pref_gr_memb
  relation_vz_rs_any_to_cons    = var.relation_vz_rs_any_to_cons
  relation_vz_rs_any_to_cons_if = var.relation_vz_rs_any_to_cons_if
  relation_vz_rs_any_to_prov    = var.relation_vz_rs_any_to_prov
  vrf_dn                        = var.vrf_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_any.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_any.this.id
}

output "match_t" {
  description = "returns a string"
  value       = aci_any.this.match_t
}

output "name_alias" {
  description = "returns a string"
  value       = aci_any.this.name_alias
}

output "pref_gr_memb" {
  description = "returns a string"
  value       = aci_any.this.pref_gr_memb
}

output "this" {
  value = aci_any.this
}
```

[top](#index)