# aci_access_port_block

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
module "aci_access_port_block" {
  source = "./modules/aci/r/aci_access_port_block"

  # access_port_selector_dn - (required) is a type of string
  access_port_selector_dn = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # from_card - (optional) is a type of string
  from_card = null
  # from_port - (optional) is a type of string
  from_port = null
  # name - (optional) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_infra_rs_acc_bndl_subgrp - (optional) is a type of string
  relation_infra_rs_acc_bndl_subgrp = null
  # to_card - (optional) is a type of string
  to_card = null
  # to_port - (optional) is a type of string
  to_port = null
}
```

[top](#index)

### Variables

```terraform
variable "access_port_selector_dn" {
  description = "(required)"
  type        = string
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

variable "from_card" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "from_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_acc_bndl_subgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to_card" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to_port" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_access_port_block" "this" {
  access_port_selector_dn           = var.access_port_selector_dn
  annotation                        = var.annotation
  description                       = var.description
  from_card                         = var.from_card
  from_port                         = var.from_port
  name                              = var.name
  name_alias                        = var.name_alias
  relation_infra_rs_acc_bndl_subgrp = var.relation_infra_rs_acc_bndl_subgrp
  to_card                           = var.to_card
  to_port                           = var.to_port
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_access_port_block.this.description
}

output "from_card" {
  description = "returns a string"
  value       = aci_access_port_block.this.from_card
}

output "from_port" {
  description = "returns a string"
  value       = aci_access_port_block.this.from_port
}

output "id" {
  description = "returns a string"
  value       = aci_access_port_block.this.id
}

output "name" {
  description = "returns a string"
  value       = aci_access_port_block.this.name
}

output "name_alias" {
  description = "returns a string"
  value       = aci_access_port_block.this.name_alias
}

output "to_card" {
  description = "returns a string"
  value       = aci_access_port_block.this.to_card
}

output "to_port" {
  description = "returns a string"
  value       = aci_access_port_block.this.to_port
}

output "this" {
  value = aci_access_port_block.this
}
```

[top](#index)