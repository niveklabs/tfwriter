# aci_fex_bundle_group

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
module "aci_fex_bundle_group" {
  source = "./modules/aci/r/aci_fex_bundle_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # fex_profile_dn - (required) is a type of string
  fex_profile_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_infra_rs_fex_bndl_grp_to_aggr_if - (optional) is a type of set of string
  relation_infra_rs_fex_bndl_grp_to_aggr_if = []
  # relation_infra_rs_mon_fex_infra_pol - (optional) is a type of string
  relation_infra_rs_mon_fex_infra_pol = null
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

variable "fex_profile_dn" {
  description = "(required)"
  type        = string
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

variable "relation_infra_rs_fex_bndl_grp_to_aggr_if" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_infra_rs_mon_fex_infra_pol" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_fex_bundle_group" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # fex_profile_dn - (required) is a type of string
  fex_profile_dn = var.fex_profile_dn
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # relation_infra_rs_fex_bndl_grp_to_aggr_if - (optional) is a type of set of string
  relation_infra_rs_fex_bndl_grp_to_aggr_if = var.relation_infra_rs_fex_bndl_grp_to_aggr_if
  # relation_infra_rs_mon_fex_infra_pol - (optional) is a type of string
  relation_infra_rs_mon_fex_infra_pol = var.relation_infra_rs_mon_fex_infra_pol
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_fex_bundle_group.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_fex_bundle_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_fex_bundle_group.this.name_alias
}

output "this" {
  value = aci_fex_bundle_group.this
}
```

[top](#index)