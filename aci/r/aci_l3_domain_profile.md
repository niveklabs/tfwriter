# aci_l3_domain_profile

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
module "aci_l3_domain_profile" {
  source = "./modules/aci/r/aci_l3_domain_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_extnw_rs_out - (optional) is a type of set of string
  relation_extnw_rs_out = []
  # relation_infra_rs_dom_vxlan_ns_def - (optional) is a type of string
  relation_infra_rs_dom_vxlan_ns_def = null
  # relation_infra_rs_vip_addr_ns - (optional) is a type of string
  relation_infra_rs_vip_addr_ns = null
  # relation_infra_rs_vlan_ns - (optional) is a type of string
  relation_infra_rs_vlan_ns = null
  # relation_infra_rs_vlan_ns_def - (optional) is a type of string
  relation_infra_rs_vlan_ns_def = null
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

variable "relation_extnw_rs_out" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_infra_rs_dom_vxlan_ns_def" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_vip_addr_ns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_vlan_ns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_vlan_ns_def" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_l3_domain_profile" "this" {
  annotation                         = var.annotation
  description                        = var.description
  name                               = var.name
  name_alias                         = var.name_alias
  relation_extnw_rs_out              = var.relation_extnw_rs_out
  relation_infra_rs_dom_vxlan_ns_def = var.relation_infra_rs_dom_vxlan_ns_def
  relation_infra_rs_vip_addr_ns      = var.relation_infra_rs_vip_addr_ns
  relation_infra_rs_vlan_ns          = var.relation_infra_rs_vlan_ns
  relation_infra_rs_vlan_ns_def      = var.relation_infra_rs_vlan_ns_def
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_l3_domain_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_l3_domain_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_l3_domain_profile.this.name_alias
}

output "this" {
  value = aci_l3_domain_profile.this
}
```

[top](#index)