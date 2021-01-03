# aci_contract_subject

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
module "aci_contract_subject" {
  source = "./modules/aci/r/aci_contract_subject"

  # annotation - (optional) is a type of string
  annotation = null
  # cons_match_t - (optional) is a type of string
  cons_match_t = null
  # contract_dn - (required) is a type of string
  contract_dn = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # prio - (optional) is a type of string
  prio = null
  # prov_match_t - (optional) is a type of string
  prov_match_t = null
  # relation_vz_rs_sdwan_pol - (optional) is a type of string
  relation_vz_rs_sdwan_pol = null
  # relation_vz_rs_subj_filt_att - (optional) is a type of set of string
  relation_vz_rs_subj_filt_att = []
  # relation_vz_rs_subj_graph_att - (optional) is a type of string
  relation_vz_rs_subj_graph_att = null
  # rev_flt_ports - (optional) is a type of string
  rev_flt_ports = null
  # target_dscp - (optional) is a type of string
  target_dscp = null
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

variable "cons_match_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract_dn" {
  description = "(required)"
  type        = string
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

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prov_match_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vz_rs_sdwan_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vz_rs_subj_filt_att" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_vz_rs_subj_graph_att" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rev_flt_ports" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_contract_subject" "this" {
  annotation                    = var.annotation
  cons_match_t                  = var.cons_match_t
  contract_dn                   = var.contract_dn
  description                   = var.description
  name                          = var.name
  name_alias                    = var.name_alias
  prio                          = var.prio
  prov_match_t                  = var.prov_match_t
  relation_vz_rs_sdwan_pol      = var.relation_vz_rs_sdwan_pol
  relation_vz_rs_subj_filt_att  = var.relation_vz_rs_subj_filt_att
  relation_vz_rs_subj_graph_att = var.relation_vz_rs_subj_graph_att
  rev_flt_ports                 = var.rev_flt_ports
  target_dscp                   = var.target_dscp
}
```

[top](#index)

### Outputs

```terraform
output "cons_match_t" {
  description = "returns a string"
  value       = aci_contract_subject.this.cons_match_t
}

output "description" {
  description = "returns a string"
  value       = aci_contract_subject.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_contract_subject.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_contract_subject.this.name_alias
}

output "prio" {
  description = "returns a string"
  value       = aci_contract_subject.this.prio
}

output "prov_match_t" {
  description = "returns a string"
  value       = aci_contract_subject.this.prov_match_t
}

output "rev_flt_ports" {
  description = "returns a string"
  value       = aci_contract_subject.this.rev_flt_ports
}

output "target_dscp" {
  description = "returns a string"
  value       = aci_contract_subject.this.target_dscp
}

output "this" {
  value = aci_contract_subject.this
}
```

[top](#index)