# aci_imported_contract

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
module "aci_imported_contract" {
  source = "./modules/aci/r/aci_imported_contract"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_vz_rs_if - (optional) is a type of string
  relation_vz_rs_if = null
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

variable "relation_vz_rs_if" {
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
resource "aci_imported_contract" "this" {
  annotation        = var.annotation
  description       = var.description
  name              = var.name
  name_alias        = var.name_alias
  relation_vz_rs_if = var.relation_vz_rs_if
  tenant_dn         = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_imported_contract.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_imported_contract.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_imported_contract.this.name_alias
}

output "this" {
  value = aci_imported_contract.this
}
```

[top](#index)