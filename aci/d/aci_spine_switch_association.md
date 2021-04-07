# aci_spine_switch_association

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
module "aci_spine_switch_association" {
  source = "./modules/aci/d/aci_spine_switch_association"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # spine_profile_dn - (required) is a type of string
  spine_profile_dn = null
  # spine_switch_association_type - (required) is a type of string
  spine_switch_association_type = null
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

variable "spine_profile_dn" {
  description = "(required)"
  type        = string
}

variable "spine_switch_association_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_spine_switch_association" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # spine_profile_dn - (required) is a type of string
  spine_profile_dn = var.spine_profile_dn
  # spine_switch_association_type - (required) is a type of string
  spine_switch_association_type = var.spine_switch_association_type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_spine_switch_association.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_spine_switch_association.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_spine_switch_association.this.name_alias
}

output "this" {
  value = aci_spine_switch_association.this
}
```

[top](#index)