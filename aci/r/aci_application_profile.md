# aci_application_profile

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
module "aci_application_profile" {
  source = "./modules/aci/r/aci_application_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # prio - (optional) is a type of string
  prio = null
  # relation_fv_rs_ap_mon_pol - (optional) is a type of string
  relation_fv_rs_ap_mon_pol = null
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

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_ap_mon_pol" {
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
resource "aci_application_profile" "this" {
  annotation                = var.annotation
  description               = var.description
  name                      = var.name
  name_alias                = var.name_alias
  prio                      = var.prio
  relation_fv_rs_ap_mon_pol = var.relation_fv_rs_ap_mon_pol
  tenant_dn                 = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_application_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_application_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_application_profile.this.name_alias
}

output "prio" {
  description = "returns a string"
  value       = aci_application_profile.this.prio
}

output "this" {
  value = aci_application_profile.this
}
```

[top](#index)