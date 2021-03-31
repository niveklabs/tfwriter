# aci_span_source_group

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
module "aci_span_source_group" {
  source = "./modules/aci/r/aci_span_source_group"

  # admin_st - (optional) is a type of string
  admin_st = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_span_rs_src_grp_to_filter_grp - (optional) is a type of string
  relation_span_rs_src_grp_to_filter_grp = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_st" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "relation_span_rs_src_grp_to_filter_grp" {
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
resource "aci_span_source_group" "this" {
  admin_st                               = var.admin_st
  annotation                             = var.annotation
  description                            = var.description
  name                                   = var.name
  name_alias                             = var.name_alias
  relation_span_rs_src_grp_to_filter_grp = var.relation_span_rs_src_grp_to_filter_grp
  tenant_dn                              = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = aci_span_source_group.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = aci_span_source_group.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_span_source_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_span_source_group.this.name_alias
}

output "this" {
  value = aci_span_source_group.this
}
```

[top](#index)