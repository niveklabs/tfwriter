# aci_spine_port_policy_group

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
module "aci_spine_port_policy_group" {
  source = "./modules/aci/r/aci_spine_port_policy_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_infra_rs_att_ent_p - (optional) is a type of string
  relation_infra_rs_att_ent_p = null
  # relation_infra_rs_cdp_if_pol - (optional) is a type of string
  relation_infra_rs_cdp_if_pol = null
  # relation_infra_rs_copp_if_pol - (optional) is a type of string
  relation_infra_rs_copp_if_pol = null
  # relation_infra_rs_h_if_pol - (optional) is a type of string
  relation_infra_rs_h_if_pol = null
  # relation_infra_rs_macsec_if_pol - (optional) is a type of string
  relation_infra_rs_macsec_if_pol = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_att_ent_p" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_cdp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_copp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_h_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_macsec_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_spine_port_policy_group" "this" {
  annotation                      = var.annotation
  description                     = var.description
  name                            = var.name
  name_alias                      = var.name_alias
  relation_infra_rs_att_ent_p     = var.relation_infra_rs_att_ent_p
  relation_infra_rs_cdp_if_pol    = var.relation_infra_rs_cdp_if_pol
  relation_infra_rs_copp_if_pol   = var.relation_infra_rs_copp_if_pol
  relation_infra_rs_h_if_pol      = var.relation_infra_rs_h_if_pol
  relation_infra_rs_macsec_if_pol = var.relation_infra_rs_macsec_if_pol
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.name_alias
}

output "relation_infra_rs_att_ent_p" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.relation_infra_rs_att_ent_p
}

output "relation_infra_rs_cdp_if_pol" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.relation_infra_rs_cdp_if_pol
}

output "relation_infra_rs_copp_if_pol" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.relation_infra_rs_copp_if_pol
}

output "relation_infra_rs_h_if_pol" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.relation_infra_rs_h_if_pol
}

output "relation_infra_rs_macsec_if_pol" {
  description = "returns a string"
  value       = aci_spine_port_policy_group.this.relation_infra_rs_macsec_if_pol
}

output "this" {
  value = aci_spine_port_policy_group.this
}
```

[top](#index)