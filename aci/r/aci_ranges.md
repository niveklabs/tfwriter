# aci_ranges

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
module "aci_ranges" {
  source = "./modules/aci/r/aci_ranges"

  # alloc_mode - (optional) is a type of string
  alloc_mode = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # from - (required) is a type of string
  from = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # role - (optional) is a type of string
  role = null
  # to - (required) is a type of string
  to = null
  # vlan_pool_dn - (required) is a type of string
  vlan_pool_dn = null
}
```

[top](#index)

### Variables

```terraform
variable "alloc_mode" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "from" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to" {
  description = "(required)"
  type        = string
}

variable "vlan_pool_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_ranges" "this" {
  alloc_mode   = var.alloc_mode
  annotation   = var.annotation
  description  = var.description
  from         = var.from
  name_alias   = var.name_alias
  role         = var.role
  to           = var.to
  vlan_pool_dn = var.vlan_pool_dn
}
```

[top](#index)

### Outputs

```terraform
output "alloc_mode" {
  description = "returns a string"
  value       = aci_ranges.this.alloc_mode
}

output "description" {
  description = "returns a string"
  value       = aci_ranges.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_ranges.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_ranges.this.name_alias
}

output "role" {
  description = "returns a string"
  value       = aci_ranges.this.role
}

output "this" {
  value = aci_ranges.this
}
```

[top](#index)