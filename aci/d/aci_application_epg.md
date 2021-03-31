# aci_application_epg

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
module "aci_application_epg" {
  source = "./modules/aci/d/aci_application_epg"

  # annotation - (optional) is a type of string
  annotation = null
  # application_profile_dn - (required) is a type of string
  application_profile_dn = null
  # description - (optional) is a type of string
  description = null
  # exception_tag - (optional) is a type of string
  exception_tag = null
  # flood_on_encap - (optional) is a type of string
  flood_on_encap = null
  # fwd_ctrl - (optional) is a type of string
  fwd_ctrl = null
  # has_mcast_source - (optional) is a type of string
  has_mcast_source = null
  # is_attr_based_epg - (optional) is a type of string
  is_attr_based_epg = null
  # match_t - (optional) is a type of string
  match_t = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pc_enf_pref - (optional) is a type of string
  pc_enf_pref = null
  # pref_gr_memb - (optional) is a type of string
  pref_gr_memb = null
  # prio - (optional) is a type of string
  prio = null
  # shutdown - (optional) is a type of string
  shutdown = null
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

variable "application_profile_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flood_on_encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fwd_ctrl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "has_mcast_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_attr_based_epg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_t" {
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

variable "pc_enf_pref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pref_gr_memb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shutdown" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_application_epg" "this" {
  annotation             = var.annotation
  application_profile_dn = var.application_profile_dn
  description            = var.description
  exception_tag          = var.exception_tag
  flood_on_encap         = var.flood_on_encap
  fwd_ctrl               = var.fwd_ctrl
  has_mcast_source       = var.has_mcast_source
  is_attr_based_epg      = var.is_attr_based_epg
  match_t                = var.match_t
  name                   = var.name
  name_alias             = var.name_alias
  pc_enf_pref            = var.pc_enf_pref
  pref_gr_memb           = var.pref_gr_memb
  prio                   = var.prio
  shutdown               = var.shutdown
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_application_epg.this.description
}

output "exception_tag" {
  description = "returns a string"
  value       = data.aci_application_epg.this.exception_tag
}

output "flood_on_encap" {
  description = "returns a string"
  value       = data.aci_application_epg.this.flood_on_encap
}

output "fwd_ctrl" {
  description = "returns a string"
  value       = data.aci_application_epg.this.fwd_ctrl
}

output "has_mcast_source" {
  description = "returns a string"
  value       = data.aci_application_epg.this.has_mcast_source
}

output "id" {
  description = "returns a string"
  value       = data.aci_application_epg.this.id
}

output "is_attr_based_epg" {
  description = "returns a string"
  value       = data.aci_application_epg.this.is_attr_based_epg
}

output "match_t" {
  description = "returns a string"
  value       = data.aci_application_epg.this.match_t
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_application_epg.this.name_alias
}

output "pc_enf_pref" {
  description = "returns a string"
  value       = data.aci_application_epg.this.pc_enf_pref
}

output "pref_gr_memb" {
  description = "returns a string"
  value       = data.aci_application_epg.this.pref_gr_memb
}

output "prio" {
  description = "returns a string"
  value       = data.aci_application_epg.this.prio
}

output "shutdown" {
  description = "returns a string"
  value       = data.aci_application_epg.this.shutdown
}

output "this" {
  value = aci_application_epg.this
}
```

[top](#index)