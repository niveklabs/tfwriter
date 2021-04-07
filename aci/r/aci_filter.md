# aci_filter

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
module "aci_filter" {
  source = "./modules/aci/r/aci_filter"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_vz_rs_filt_graph_att - (optional) is a type of string
  relation_vz_rs_filt_graph_att = null
  # relation_vz_rs_fwd_r_flt_p_att - (optional) is a type of string
  relation_vz_rs_fwd_r_flt_p_att = null
  # relation_vz_rs_rev_r_flt_p_att - (optional) is a type of string
  relation_vz_rs_rev_r_flt_p_att = null
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

variable "relation_vz_rs_filt_graph_att" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vz_rs_fwd_r_flt_p_att" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vz_rs_rev_r_flt_p_att" {
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

### Resource

```terraform
resource "aci_filter" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # relation_vz_rs_filt_graph_att - (optional) is a type of string
  relation_vz_rs_filt_graph_att = var.relation_vz_rs_filt_graph_att
  # relation_vz_rs_fwd_r_flt_p_att - (optional) is a type of string
  relation_vz_rs_fwd_r_flt_p_att = var.relation_vz_rs_fwd_r_flt_p_att
  # relation_vz_rs_rev_r_flt_p_att - (optional) is a type of string
  relation_vz_rs_rev_r_flt_p_att = var.relation_vz_rs_rev_r_flt_p_att
  # tenant_dn - (required) is a type of string
  tenant_dn = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_filter.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_filter.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_filter.this.name_alias
}

output "this" {
  value = aci_filter.this
}
```

[top](#index)