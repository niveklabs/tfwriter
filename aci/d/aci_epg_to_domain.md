# aci_epg_to_domain

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
module "aci_epg_to_domain" {
  source = "./modules/aci/d/aci_epg_to_domain"

  # allow_micro_seg - (optional) is a type of bool
  allow_micro_seg = null
  # annotation - (optional) is a type of string
  annotation = null
  # application_epg_dn - (required) is a type of string
  application_epg_dn = null
  # binding_type - (optional) is a type of string
  binding_type = null
  # delimiter - (optional) is a type of string
  delimiter = null
  # description - (optional) is a type of string
  description = null
  # encap - (optional) is a type of string
  encap = null
  # encap_mode - (optional) is a type of string
  encap_mode = null
  # epg_cos - (optional) is a type of string
  epg_cos = null
  # epg_cos_pref - (optional) is a type of string
  epg_cos_pref = null
  # instr_imedcy - (optional) is a type of string
  instr_imedcy = null
  # lag_policy_name - (optional) is a type of string
  lag_policy_name = null
  # netflow_dir - (optional) is a type of string
  netflow_dir = null
  # netflow_pref - (optional) is a type of string
  netflow_pref = null
  # num_ports - (optional) is a type of string
  num_ports = null
  # port_allocation - (optional) is a type of string
  port_allocation = null
  # primary_encap - (optional) is a type of string
  primary_encap = null
  # primary_encap_inner - (optional) is a type of string
  primary_encap_inner = null
  # res_imedcy - (optional) is a type of string
  res_imedcy = null
  # secondary_encap_inner - (optional) is a type of string
  secondary_encap_inner = null
  # switching_mode - (optional) is a type of string
  switching_mode = null
  # tdn - (required) is a type of string
  tdn = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_micro_seg" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_epg_dn" {
  description = "(required)"
  type        = string
}

variable "binding_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delimiter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "epg_cos" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "epg_cos_pref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instr_imedcy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lag_policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netflow_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netflow_pref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_ports" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_allocation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_encap_inner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "res_imedcy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_encap_inner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switching_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tdn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_epg_to_domain" "this" {
  allow_micro_seg       = var.allow_micro_seg
  annotation            = var.annotation
  application_epg_dn    = var.application_epg_dn
  binding_type          = var.binding_type
  delimiter             = var.delimiter
  description           = var.description
  encap                 = var.encap
  encap_mode            = var.encap_mode
  epg_cos               = var.epg_cos
  epg_cos_pref          = var.epg_cos_pref
  instr_imedcy          = var.instr_imedcy
  lag_policy_name       = var.lag_policy_name
  netflow_dir           = var.netflow_dir
  netflow_pref          = var.netflow_pref
  num_ports             = var.num_ports
  port_allocation       = var.port_allocation
  primary_encap         = var.primary_encap
  primary_encap_inner   = var.primary_encap_inner
  res_imedcy            = var.res_imedcy
  secondary_encap_inner = var.secondary_encap_inner
  switching_mode        = var.switching_mode
  tdn                   = var.tdn
}
```

[top](#index)

### Outputs

```terraform
output "allow_micro_seg" {
  description = "returns a bool"
  value       = data.aci_epg_to_domain.this.allow_micro_seg
}

output "binding_type" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.binding_type
}

output "delimiter" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.delimiter
}

output "description" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.description
}

output "encap" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.encap
}

output "encap_mode" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.encap_mode
}

output "epg_cos" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.epg_cos
}

output "epg_cos_pref" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.epg_cos_pref
}

output "id" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.id
}

output "instr_imedcy" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.instr_imedcy
}

output "lag_policy_name" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.lag_policy_name
}

output "netflow_dir" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.netflow_dir
}

output "netflow_pref" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.netflow_pref
}

output "num_ports" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.num_ports
}

output "port_allocation" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.port_allocation
}

output "primary_encap" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.primary_encap
}

output "primary_encap_inner" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.primary_encap_inner
}

output "res_imedcy" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.res_imedcy
}

output "secondary_encap_inner" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.secondary_encap_inner
}

output "switching_mode" {
  description = "returns a string"
  value       = data.aci_epg_to_domain.this.switching_mode
}

output "this" {
  value = aci_epg_to_domain.this
}
```

[top](#index)