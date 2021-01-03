# aci_leaf_access_bundle_policy_group

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
module "aci_leaf_access_bundle_policy_group" {
  source = "./modules/aci/d/aci_leaf_access_bundle_policy_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # lag_t - (optional) is a type of string
  lag_t = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lag_t" {
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
data "aci_leaf_access_bundle_policy_group" "this" {
  annotation  = var.annotation
  description = var.description
  lag_t       = var.lag_t
  name        = var.name
  name_alias  = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_leaf_access_bundle_policy_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_leaf_access_bundle_policy_group.this.id
}

output "lag_t" {
  description = "returns a string"
  value       = data.aci_leaf_access_bundle_policy_group.this.lag_t
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_leaf_access_bundle_policy_group.this.name_alias
}

output "this" {
  value = aci_leaf_access_bundle_policy_group.this
}
```

[top](#index)