# aci_contract

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
module "aci_contract" {
  source = "./modules/aci/d/aci_contract"

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
  # scope - (optional) is a type of string
  scope = null
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

variable "scope" {
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
data "aci_contract" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # prio - (optional) is a type of string
  prio = var.prio
  # scope - (optional) is a type of string
  scope = var.scope
  # target_dscp - (optional) is a type of string
  target_dscp = var.target_dscp
  # tenant_dn - (required) is a type of string
  tenant_dn = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_contract.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_contract.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_contract.this.name_alias
}

output "prio" {
  description = "returns a string"
  value       = data.aci_contract.this.prio
}

output "scope" {
  description = "returns a string"
  value       = data.aci_contract.this.scope
}

output "target_dscp" {
  description = "returns a string"
  value       = data.aci_contract.this.target_dscp
}

output "this" {
  value = aci_contract.this
}
```

[top](#index)