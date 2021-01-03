# aci_l2_interface_policy

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_l2_interface_policy" {
  source = "./modules/aci/d/aci_l2_interface_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # qinq - (optional) is a type of string
  qinq = null
  # vepa - (optional) is a type of string
  vepa = null
  # vlan_scope - (optional) is a type of string
  vlan_scope = null
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

variable "qinq" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vepa" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_scope" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_l2_interface_policy" "this" {
  annotation  = var.annotation
  description = var.description
  name        = var.name
  name_alias  = var.name_alias
  qinq        = var.qinq
  vepa        = var.vepa
  vlan_scope  = var.vlan_scope
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_l2_interface_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_l2_interface_policy.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_l2_interface_policy.this.name_alias
}

output "qinq" {
  description = "returns a string"
  value       = data.aci_l2_interface_policy.this.qinq
}

output "vepa" {
  description = "returns a string"
  value       = data.aci_l2_interface_policy.this.vepa
}

output "vlan_scope" {
  description = "returns a string"
  value       = data.aci_l2_interface_policy.this.vlan_scope
}

output "this" {
  value = aci_l2_interface_policy.this
}
```

[top](#index)