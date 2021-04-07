# mso_schema_site_external_epg_selector

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "mso_schema_site_external_epg_selector" {
  source = "./modules/mso/d/mso_schema_site_external_epg_selector"

  # external_epg_name - (required) is a type of string
  external_epg_name = null
  # ip - (optional) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "external_epg_name" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
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

### Datasource

```terraform
data "mso_schema_site_external_epg_selector" "this" {
  # external_epg_name - (required) is a type of string
  external_epg_name = var.external_epg_name
  # ip - (optional) is a type of string
  ip = var.ip
  # name - (required) is a type of string
  name = var.name
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # site_id - (required) is a type of string
  site_id = var.site_id
  # template_name - (required) is a type of string
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_site_external_epg_selector.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.mso_schema_site_external_epg_selector.this.ip
}

output "this" {
  value = mso_schema_site_external_epg_selector.this
}
```

[top](#index)