# mso_schema_site_bd_l3out

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
module "mso_schema_site_bd_l3out" {
  source = "./modules/mso/d/mso_schema_site_bd_l3out"

  # bd_name - (required) is a type of string
  bd_name = null
  # l3out_name - (required) is a type of string
  l3out_name = null
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
variable "bd_name" {
  description = "(required)"
  type        = string
}

variable "l3out_name" {
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
data "mso_schema_site_bd_l3out" "this" {
  # bd_name - (required) is a type of string
  bd_name = var.bd_name
  # l3out_name - (required) is a type of string
  l3out_name = var.l3out_name
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
  value       = data.mso_schema_site_bd_l3out.this.id
}

output "this" {
  value = mso_schema_site_bd_l3out.this
}
```

[top](#index)