# aci_tenant

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
module "aci_tenant" {
  source = "./modules/aci/r/aci_tenant"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_fv_rs_tenant_mon_pol - (optional) is a type of string
  relation_fv_rs_tenant_mon_pol = null
  # relation_fv_rs_tn_deny_rule - (optional) is a type of set of string
  relation_fv_rs_tn_deny_rule = []
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

variable "relation_fv_rs_tenant_mon_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_tn_deny_rule" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_tenant" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # relation_fv_rs_tenant_mon_pol - (optional) is a type of string
  relation_fv_rs_tenant_mon_pol = var.relation_fv_rs_tenant_mon_pol
  # relation_fv_rs_tn_deny_rule - (optional) is a type of set of string
  relation_fv_rs_tn_deny_rule = var.relation_fv_rs_tn_deny_rule
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_tenant.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_tenant.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_tenant.this.name_alias
}

output "this" {
  value = aci_tenant.this
}
```

[top](#index)