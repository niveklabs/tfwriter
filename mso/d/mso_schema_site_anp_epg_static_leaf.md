# mso_schema_site_anp_epg_static_leaf

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
module "mso_schema_site_anp_epg_static_leaf" {
  source = "./modules/mso/d/mso_schema_site_anp_epg_static_leaf"

  # anp_name - (required) is a type of string
  anp_name = null
  # epg_name - (required) is a type of string
  epg_name = null
  # path - (required) is a type of string
  path = null
  # port_encap_vlan - (optional) is a type of number
  port_encap_vlan = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (optional) is a type of string
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

variable "epg_name" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "port_encap_vlan" {
  description = "(optional)"
  type        = number
  default     = null
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
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_site_anp_epg_static_leaf" "this" {
  # anp_name - (required) is a type of string
  anp_name = var.anp_name
  # epg_name - (required) is a type of string
  epg_name = var.epg_name
  # path - (required) is a type of string
  path = var.path
  # port_encap_vlan - (optional) is a type of number
  port_encap_vlan = var.port_encap_vlan
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # site_id - (required) is a type of string
  site_id = var.site_id
  # template_name - (optional) is a type of string
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_static_leaf.this.id
}

output "template_name" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_static_leaf.this.template_name
}

output "this" {
  value = mso_schema_site_anp_epg_static_leaf.this
}
```

[top](#index)