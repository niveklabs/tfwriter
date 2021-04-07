# aci_logical_interface_profile

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
module "aci_logical_interface_profile" {
  source = "./modules/aci/d/aci_logical_interface_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # logical_node_profile_dn - (required) is a type of string
  logical_node_profile_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # prio - (optional) is a type of string
  prio = null
  # tag - (optional) is a type of string
  tag = null
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

variable "logical_node_profile_dn" {
  description = "(required)"
  type        = string
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

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_logical_interface_profile" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # logical_node_profile_dn - (required) is a type of string
  logical_node_profile_dn = var.logical_node_profile_dn
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # prio - (optional) is a type of string
  prio = var.prio
  # tag - (optional) is a type of string
  tag = var.tag
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_logical_interface_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_logical_interface_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_logical_interface_profile.this.name_alias
}

output "prio" {
  description = "returns a string"
  value       = data.aci_logical_interface_profile.this.prio
}

output "tag" {
  description = "returns a string"
  value       = data.aci_logical_interface_profile.this.tag
}

output "this" {
  value = aci_logical_interface_profile.this
}
```

[top](#index)