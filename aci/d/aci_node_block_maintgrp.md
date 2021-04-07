# aci_node_block_maintgrp

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
module "aci_node_block_maintgrp" {
  source = "./modules/aci/d/aci_node_block_maintgrp"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # from_ - (optional) is a type of string
  from_ = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pod_maintenance_group_dn - (required) is a type of string
  pod_maintenance_group_dn = null
  # to_ - (optional) is a type of string
  to_ = null
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

variable "from_" {
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

variable "pod_maintenance_group_dn" {
  description = "(required)"
  type        = string
}

variable "to_" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_node_block_maintgrp" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # from_ - (optional) is a type of string
  from_ = var.from_
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # pod_maintenance_group_dn - (required) is a type of string
  pod_maintenance_group_dn = var.pod_maintenance_group_dn
  # to_ - (optional) is a type of string
  to_ = var.to_
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_node_block_maintgrp.this.description
}

output "from_" {
  description = "returns a string"
  value       = data.aci_node_block_maintgrp.this.from_
}

output "id" {
  description = "returns a string"
  value       = data.aci_node_block_maintgrp.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_node_block_maintgrp.this.name_alias
}

output "to_" {
  description = "returns a string"
  value       = data.aci_node_block_maintgrp.this.to_
}

output "this" {
  value = aci_node_block_maintgrp.this
}
```

[top](#index)