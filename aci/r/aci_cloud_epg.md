# aci_cloud_epg

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
module "aci_cloud_epg" {
  source = "./modules/aci/r/aci_cloud_epg"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_applicationcontainer_dn - (required) is a type of string
  cloud_applicationcontainer_dn = null
  # description - (optional) is a type of string
  description = null
  # exception_tag - (optional) is a type of string
  exception_tag = null
  # flood_on_encap - (optional) is a type of string
  flood_on_encap = null
  # match_t - (optional) is a type of string
  match_t = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pref_gr_memb - (optional) is a type of string
  pref_gr_memb = null
  # prio - (optional) is a type of string
  prio = null
  # relation_cloud_rs_cloud_epg_ctx - (optional) is a type of string
  relation_cloud_rs_cloud_epg_ctx = null
  # relation_fv_rs_cons - (optional) is a type of set of string
  relation_fv_rs_cons = []
  # relation_fv_rs_cons_if - (optional) is a type of set of string
  relation_fv_rs_cons_if = []
  # relation_fv_rs_cust_qos_pol - (optional) is a type of string
  relation_fv_rs_cust_qos_pol = null
  # relation_fv_rs_intra_epg - (optional) is a type of set of string
  relation_fv_rs_intra_epg = []
  # relation_fv_rs_prot_by - (optional) is a type of set of string
  relation_fv_rs_prot_by = []
  # relation_fv_rs_prov - (optional) is a type of set of string
  relation_fv_rs_prov = []
  # relation_fv_rs_sec_inherited - (optional) is a type of set of string
  relation_fv_rs_sec_inherited = []
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

variable "cloud_applicationcontainer_dn" {
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

variable "relation_cloud_rs_cloud_epg_ctx" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_cons" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_cons_if" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_cust_qos_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_intra_epg" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_prot_by" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_prov" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_sec_inherited" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_cloud_epg" "this" {
  annotation                      = var.annotation
  cloud_applicationcontainer_dn   = var.cloud_applicationcontainer_dn
  description                     = var.description
  exception_tag                   = var.exception_tag
  flood_on_encap                  = var.flood_on_encap
  match_t                         = var.match_t
  name                            = var.name
  name_alias                      = var.name_alias
  pref_gr_memb                    = var.pref_gr_memb
  prio                            = var.prio
  relation_cloud_rs_cloud_epg_ctx = var.relation_cloud_rs_cloud_epg_ctx
  relation_fv_rs_cons             = var.relation_fv_rs_cons
  relation_fv_rs_cons_if          = var.relation_fv_rs_cons_if
  relation_fv_rs_cust_qos_pol     = var.relation_fv_rs_cust_qos_pol
  relation_fv_rs_intra_epg        = var.relation_fv_rs_intra_epg
  relation_fv_rs_prot_by          = var.relation_fv_rs_prot_by
  relation_fv_rs_prov             = var.relation_fv_rs_prov
  relation_fv_rs_sec_inherited    = var.relation_fv_rs_sec_inherited
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_cloud_epg.this.description
}

output "exception_tag" {
  description = "returns a string"
  value       = aci_cloud_epg.this.exception_tag
}

output "flood_on_encap" {
  description = "returns a string"
  value       = aci_cloud_epg.this.flood_on_encap
}

output "id" {
  description = "returns a string"
  value       = aci_cloud_epg.this.id
}

output "match_t" {
  description = "returns a string"
  value       = aci_cloud_epg.this.match_t
}

output "name_alias" {
  description = "returns a string"
  value       = aci_cloud_epg.this.name_alias
}

output "pref_gr_memb" {
  description = "returns a string"
  value       = aci_cloud_epg.this.pref_gr_memb
}

output "prio" {
  description = "returns a string"
  value       = aci_cloud_epg.this.prio
}

output "this" {
  value = aci_cloud_epg.this
}
```

[top](#index)