# aci_cdp_interface_policy

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
module "aci_cdp_interface_policy" {
  source = "./modules/aci/d/aci_cdp_interface_policy"

  # admin_st - (optional) is a type of string
  admin_st = null
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
variable "admin_st" {
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
data "aci_cdp_interface_policy" "this" {
  admin_st    = var.admin_st
  annotation  = var.annotation
  description = var.description
  name        = var.name
  name_alias  = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = data.aci_cdp_interface_policy.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = data.aci_cdp_interface_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cdp_interface_policy.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cdp_interface_policy.this.name_alias
}

output "this" {
  value = aci_cdp_interface_policy.this
}
```

[top](#index)