# mso_schema_site_vrf

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
module "mso_schema_site_vrf" {
  source = "./modules/mso/d/mso_schema_site_vrf"

  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (optional) is a type of string
  template_name = null
  # vrf_name - (required) is a type of string
  vrf_name = null
}
```

[top](#index)

### Variables

```terraform
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

variable "vrf_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_site_vrf" "this" {
  schema_id     = var.schema_id
  site_id       = var.site_id
  template_name = var.template_name
  vrf_name      = var.vrf_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_site_vrf.this.id
}

output "this" {
  value = mso_schema_site_vrf.this
}
```

[top](#index)