# aci_fc_domain

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
module "aci_fc_domain" {
  source = "./modules/aci/r/aci_fc_domain"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_fc_rs_vsan_attr - (optional) is a type of string
  relation_fc_rs_vsan_attr = null
  # relation_fc_rs_vsan_attr_def - (optional) is a type of string
  relation_fc_rs_vsan_attr_def = null
  # relation_fc_rs_vsan_ns - (optional) is a type of string
  relation_fc_rs_vsan_ns = null
  # relation_fc_rs_vsan_ns_def - (optional) is a type of string
  relation_fc_rs_vsan_ns_def = null
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

variable "relation_fc_rs_vsan_attr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fc_rs_vsan_attr_def" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fc_rs_vsan_ns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fc_rs_vsan_ns_def" {
  description = "(optional)"
  type        = string
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
resource "aci_fc_domain" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # relation_fc_rs_vsan_attr - (optional) is a type of string
  relation_fc_rs_vsan_attr = var.relation_fc_rs_vsan_attr
  # relation_fc_rs_vsan_attr_def - (optional) is a type of string
  relation_fc_rs_vsan_attr_def = var.relation_fc_rs_vsan_attr_def
  # relation_fc_rs_vsan_ns - (optional) is a type of string
  relation_fc_rs_vsan_ns = var.relation_fc_rs_vsan_ns
  # relation_fc_rs_vsan_ns_def - (optional) is a type of string
  relation_fc_rs_vsan_ns_def = var.relation_fc_rs_vsan_ns_def
  # relation_infra_rs_dom_vxlan_ns_def - (optional) is a type of string
  relation_infra_rs_dom_vxlan_ns_def = var.relation_infra_rs_dom_vxlan_ns_def
  # relation_infra_rs_vip_addr_ns - (optional) is a type of string
  relation_infra_rs_vip_addr_ns = var.relation_infra_rs_vip_addr_ns
  # relation_infra_rs_vlan_ns - (optional) is a type of string
  relation_infra_rs_vlan_ns = var.relation_infra_rs_vlan_ns
  # relation_infra_rs_vlan_ns_def - (optional) is a type of string
  relation_infra_rs_vlan_ns_def = var.relation_infra_rs_vlan_ns_def
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_fc_domain.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_fc_domain.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_fc_domain.this.name_alias
}

output "this" {
  value = aci_fc_domain.this
}
```

[top](#index)