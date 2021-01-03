# aci_vlan_pool

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
module "aci_vlan_pool" {
  source = "./modules/aci/d/aci_vlan_pool"

  # alloc_mode - (required) is a type of string
  alloc_mode = null
  # annotation - (optional) is a type of string
  annotation = null
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
variable "alloc_mode" {
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
data "aci_vlan_pool" "this" {
  alloc_mode  = var.alloc_mode
  annotation  = var.annotation
  description = var.description
  name        = var.name
  name_alias  = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_vlan_pool.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_vlan_pool.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_vlan_pool.this.name_alias
}

output "this" {
  value = aci_vlan_pool.this
}
```

[top](#index)