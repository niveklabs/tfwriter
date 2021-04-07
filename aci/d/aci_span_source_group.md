# aci_span_source_group

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
module "aci_span_source_group" {
  source = "./modules/aci/d/aci_span_source_group"

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
  # tenant_dn - (required) is a type of string
  tenant_dn = null
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

variable "tenant_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_span_source_group" "this" {
  # admin_st - (optional) is a type of string
  admin_st = var.admin_st
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # tenant_dn - (required) is a type of string
  tenant_dn = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = data.aci_span_source_group.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = data.aci_span_source_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_span_source_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_span_source_group.this.name_alias
}

output "this" {
  value = aci_span_source_group.this
}
```

[top](#index)