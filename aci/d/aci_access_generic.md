# aci_access_generic

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
module "aci_access_generic" {
  source = "./modules/aci/d/aci_access_generic"

  # annotation - (optional) is a type of string
  annotation = null
  # attachable_access_entity_profile_dn - (required) is a type of string
  attachable_access_entity_profile_dn = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
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

variable "attachable_access_entity_profile_dn" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "aci_access_generic" "this" {
  annotation                          = var.annotation
  attachable_access_entity_profile_dn = var.attachable_access_entity_profile_dn
  description                         = var.description
  name                                = var.name
  name_alias                          = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_access_generic.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_access_generic.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_access_generic.this.name_alias
}

output "this" {
  value = aci_access_generic.this
}
```

[top](#index)