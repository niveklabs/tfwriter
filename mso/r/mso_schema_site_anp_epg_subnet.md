# mso_schema_site_anp_epg_subnet

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
module "mso_schema_site_anp_epg_subnet" {
  source = "./modules/mso/r/mso_schema_site_anp_epg_subnet"

  # anp_name - (required) is a type of string
  anp_name = null
  # description - (optional) is a type of string
  description = null
  # epg_name - (required) is a type of string
  epg_name = null
  # ip - (required) is a type of string
  ip = null
  # no_default_gateway - (optional) is a type of bool
  no_default_gateway = null
  # querier - (optional) is a type of bool
  querier = null
  # schema_id - (required) is a type of string
  schema_id = null
  # scope - (required) is a type of string
  scope = null
  # shared - (required) is a type of bool
  shared = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "anp_name" {
  description = "(required)"
  type        = string
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

variable "ip" {
  description = "(required)"
  type        = string
}

variable "no_default_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "querier" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "shared" {
  description = "(required)"
  type        = bool
}

variable "site_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_site_anp_epg_subnet" "this" {
  # anp_name - (required) is a type of string
  anp_name = var.anp_name
  # description - (optional) is a type of string
  description = var.description
  # epg_name - (required) is a type of string
  epg_name = var.epg_name
  # ip - (required) is a type of string
  ip = var.ip
  # no_default_gateway - (optional) is a type of bool
  no_default_gateway = var.no_default_gateway
  # querier - (optional) is a type of bool
  querier = var.querier
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # scope - (required) is a type of string
  scope = var.scope
  # shared - (required) is a type of bool
  shared = var.shared
  # site_id - (required) is a type of string
  site_id = var.site_id
  # template_name - (required) is a type of string
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = mso_schema_site_anp_epg_subnet.this.description
}

output "id" {
  description = "returns a string"
  value       = mso_schema_site_anp_epg_subnet.this.id
}

output "no_default_gateway" {
  description = "returns a bool"
  value       = mso_schema_site_anp_epg_subnet.this.no_default_gateway
}

output "querier" {
  description = "returns a bool"
  value       = mso_schema_site_anp_epg_subnet.this.querier
}

output "this" {
  value = mso_schema_site_anp_epg_subnet.this
}
```

[top](#index)