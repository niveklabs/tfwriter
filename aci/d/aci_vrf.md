# aci_vrf

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
module "aci_vrf" {
  source = "./modules/aci/d/aci_vrf"

  # annotation - (optional) is a type of string
  annotation = null
  # bd_enforced_enable - (optional) is a type of string
  bd_enforced_enable = null
  # description - (optional) is a type of string
  description = null
  # ip_data_plane_learning - (optional) is a type of string
  ip_data_plane_learning = null
  # knw_mcast_act - (optional) is a type of string
  knw_mcast_act = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pc_enf_dir - (optional) is a type of string
  pc_enf_dir = null
  # pc_enf_pref - (optional) is a type of string
  pc_enf_pref = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
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

variable "bd_enforced_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_data_plane_learning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "knw_mcast_act" {
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

variable "pc_enf_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pc_enf_pref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_vrf" "this" {
  annotation             = var.annotation
  bd_enforced_enable     = var.bd_enforced_enable
  description            = var.description
  ip_data_plane_learning = var.ip_data_plane_learning
  knw_mcast_act          = var.knw_mcast_act
  name                   = var.name
  name_alias             = var.name_alias
  pc_enf_dir             = var.pc_enf_dir
  pc_enf_pref            = var.pc_enf_pref
  tenant_dn              = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "bd_enforced_enable" {
  description = "returns a string"
  value       = data.aci_vrf.this.bd_enforced_enable
}

output "description" {
  description = "returns a string"
  value       = data.aci_vrf.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_vrf.this.id
}

output "ip_data_plane_learning" {
  description = "returns a string"
  value       = data.aci_vrf.this.ip_data_plane_learning
}

output "knw_mcast_act" {
  description = "returns a string"
  value       = data.aci_vrf.this.knw_mcast_act
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_vrf.this.name_alias
}

output "pc_enf_dir" {
  description = "returns a string"
  value       = data.aci_vrf.this.pc_enf_dir
}

output "pc_enf_pref" {
  description = "returns a string"
  value       = data.aci_vrf.this.pc_enf_pref
}

output "this" {
  value = aci_vrf.this
}
```

[top](#index)