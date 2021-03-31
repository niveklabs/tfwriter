# aci_l3_outside

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
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_l3_outside" {
  source = "./modules/aci/d/aci_l3_outside"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # enforce_rtctrl - (optional) is a type of string
  enforce_rtctrl = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # target_dscp - (optional) is a type of string
  target_dscp = null
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

variable "enforce_rtctrl" {
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

variable "target_dscp" {
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
data "aci_l3_outside" "this" {
  annotation     = var.annotation
  description    = var.description
  enforce_rtctrl = var.enforce_rtctrl
  name           = var.name
  name_alias     = var.name_alias
  target_dscp    = var.target_dscp
  tenant_dn      = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_l3_outside.this.description
}

output "enforce_rtctrl" {
  description = "returns a string"
  value       = data.aci_l3_outside.this.enforce_rtctrl
}

output "id" {
  description = "returns a string"
  value       = data.aci_l3_outside.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_l3_outside.this.name_alias
}

output "target_dscp" {
  description = "returns a string"
  value       = data.aci_l3_outside.this.target_dscp
}

output "this" {
  value = aci_l3_outside.this
}
```

[top](#index)