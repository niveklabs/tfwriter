# mso_schema_site_anp_epg_domain

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_site_anp_epg_domain" {
  source = "./modules/mso/d/mso_schema_site_anp_epg_domain"

  # allow_micro_segmentation - (optional) is a type of bool
  allow_micro_segmentation = null
  # anp_name - (required) is a type of string
  anp_name = null
  # deployment_immediacy - (optional) is a type of string
  deployment_immediacy = null
  # dn - (required) is a type of string
  dn = null
  # domain_type - (required) is a type of string
  domain_type = null
  # enhanced_lag_policy_dn - (optional) is a type of string
  enhanced_lag_policy_dn = null
  # enhanced_lag_policy_name - (optional) is a type of string
  enhanced_lag_policy_name = null
  # epg_name - (required) is a type of string
  epg_name = null
  # micro_seg_vlan - (optional) is a type of number
  micro_seg_vlan = null
  # micro_seg_vlan_type - (optional) is a type of string
  micro_seg_vlan_type = null
  # port_encap_vlan - (optional) is a type of number
  port_encap_vlan = null
  # port_encap_vlan_type - (optional) is a type of string
  port_encap_vlan_type = null
  # resolution_immediacy - (optional) is a type of string
  resolution_immediacy = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # switch_type - (optional) is a type of string
  switch_type = null
  # switching_mode - (optional) is a type of string
  switching_mode = null
  # template_name - (optional) is a type of string
  template_name = null
  # vlan_encap_mode - (optional) is a type of string
  vlan_encap_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_micro_segmentation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "anp_name" {
  description = "(required)"
  type        = string
}

variable "deployment_immediacy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dn" {
  description = "(required)"
  type        = string
}

variable "domain_type" {
  description = "(required)"
  type        = string
}

variable "enhanced_lag_policy_dn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enhanced_lag_policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "epg_name" {
  description = "(required)"
  type        = string
}

variable "micro_seg_vlan" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "micro_seg_vlan_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_encap_vlan" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_encap_vlan_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolution_immediacy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "site_id" {
  description = "(required)"
  type        = string
}

variable "switch_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switching_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_encap_mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_site_anp_epg_domain" "this" {
  allow_micro_segmentation = var.allow_micro_segmentation
  anp_name                 = var.anp_name
  deployment_immediacy     = var.deployment_immediacy
  dn                       = var.dn
  domain_type              = var.domain_type
  enhanced_lag_policy_dn   = var.enhanced_lag_policy_dn
  enhanced_lag_policy_name = var.enhanced_lag_policy_name
  epg_name                 = var.epg_name
  micro_seg_vlan           = var.micro_seg_vlan
  micro_seg_vlan_type      = var.micro_seg_vlan_type
  port_encap_vlan          = var.port_encap_vlan
  port_encap_vlan_type     = var.port_encap_vlan_type
  resolution_immediacy     = var.resolution_immediacy
  schema_id                = var.schema_id
  site_id                  = var.site_id
  switch_type              = var.switch_type
  switching_mode           = var.switching_mode
  template_name            = var.template_name
  vlan_encap_mode          = var.vlan_encap_mode
}
```

[top](#index)

### Outputs

```terraform
output "allow_micro_segmentation" {
  description = "returns a bool"
  value       = data.mso_schema_site_anp_epg_domain.this.allow_micro_segmentation
}

output "enhanced_lag_policy_dn" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.enhanced_lag_policy_dn
}

output "enhanced_lag_policy_name" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.enhanced_lag_policy_name
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.id
}

output "micro_seg_vlan" {
  description = "returns a number"
  value       = data.mso_schema_site_anp_epg_domain.this.micro_seg_vlan
}

output "micro_seg_vlan_type" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.micro_seg_vlan_type
}

output "port_encap_vlan" {
  description = "returns a number"
  value       = data.mso_schema_site_anp_epg_domain.this.port_encap_vlan
}

output "port_encap_vlan_type" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.port_encap_vlan_type
}

output "resolution_immediacy" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.resolution_immediacy
}

output "switch_type" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.switch_type
}

output "switching_mode" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.switching_mode
}

output "vlan_encap_mode" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_domain.this.vlan_encap_mode
}

output "this" {
  value = mso_schema_site_anp_epg_domain.this
}
```

[top](#index)