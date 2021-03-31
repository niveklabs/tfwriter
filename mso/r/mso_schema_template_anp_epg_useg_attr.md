# mso_schema_template_anp_epg_useg_attr

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_anp_epg_useg_attr" {
  source = "./modules/mso/r/mso_schema_template_anp_epg_useg_attr"

  # anp_name - (required) is a type of string
  anp_name = null
  # category - (optional) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # epg_name - (required) is a type of string
  epg_name = null
  # name - (required) is a type of string
  name = null
  # operator - (optional) is a type of string
  operator = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null
  # useg_subnet - (optional) is a type of bool
  useg_subnet = null
  # useg_type - (required) is a type of string
  useg_type = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "anp_name" {
  description = "(required)"
  type        = string
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "epg_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "operator" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "useg_subnet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "useg_type" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_anp_epg_useg_attr" "this" {
  anp_name      = var.anp_name
  category      = var.category
  description   = var.description
  epg_name      = var.epg_name
  name          = var.name
  operator      = var.operator
  schema_id     = var.schema_id
  template_name = var.template_name
  useg_subnet   = var.useg_subnet
  useg_type     = var.useg_type
  value         = var.value
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = mso_schema_template_anp_epg_useg_attr.this.category
}

output "description" {
  description = "returns a string"
  value       = mso_schema_template_anp_epg_useg_attr.this.description
}

output "id" {
  description = "returns a string"
  value       = mso_schema_template_anp_epg_useg_attr.this.id
}

output "operator" {
  description = "returns a string"
  value       = mso_schema_template_anp_epg_useg_attr.this.operator
}

output "useg_subnet" {
  description = "returns a bool"
  value       = mso_schema_template_anp_epg_useg_attr.this.useg_subnet
}

output "this" {
  value = mso_schema_template_anp_epg_useg_attr.this
}
```

[top](#index)