# mso_schema_site_anp_epg

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
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_site_anp_epg" {
  source = "./modules/mso/d/mso_schema_site_anp_epg"

  # anp_name - (required) is a type of string
  anp_name = null
  # epg_name - (required) is a type of string
  epg_name = null
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
data "mso_schema_site_anp_epg" "this" {
  anp_name      = var.anp_name
  epg_name      = var.epg_name
  schema_id     = var.schema_id
  site_id       = var.site_id
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg.this.id
}

output "template_name" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg.this.template_name
}

output "this" {
  value = mso_schema_site_anp_epg.this
}
```

[top](#index)