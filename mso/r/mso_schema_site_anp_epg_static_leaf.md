# mso_schema_site_anp_epg_static_leaf

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
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_site_anp_epg_static_leaf" {
  source = "./modules/mso/r/mso_schema_site_anp_epg_static_leaf"

  # anp_name - (required) is a type of string
  anp_name = null
  # epg_name - (required) is a type of string
  epg_name = null
  # path - (required) is a type of string
  path = null
  # port_encap_vlan - (required) is a type of number
  port_encap_vlan = null
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
  description = "(required)"
  type        = number
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

### Resource

```terraform
resource "mso_schema_site_anp_epg_static_leaf" "this" {
  anp_name        = var.anp_name
  epg_name        = var.epg_name
  path            = var.path
  port_encap_vlan = var.port_encap_vlan
  schema_id       = var.schema_id
  site_id         = var.site_id
  template_name   = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_site_anp_epg_static_leaf.this.id
}

output "this" {
  value = mso_schema_site_anp_epg_static_leaf.this
}
```

[top](#index)