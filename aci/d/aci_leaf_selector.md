# aci_leaf_selector

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
module "aci_leaf_selector" {
  source = "./modules/aci/d/aci_leaf_selector"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # leaf_profile_dn - (required) is a type of string
  leaf_profile_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # switch_association_type - (required) is a type of string
  switch_association_type = null
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

variable "leaf_profile_dn" {
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

variable "switch_association_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_leaf_selector" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # leaf_profile_dn - (required) is a type of string
  leaf_profile_dn = var.leaf_profile_dn
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # switch_association_type - (required) is a type of string
  switch_association_type = var.switch_association_type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_leaf_selector.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_leaf_selector.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_leaf_selector.this.name_alias
}

output "this" {
  value = aci_leaf_selector.this
}
```

[top](#index)