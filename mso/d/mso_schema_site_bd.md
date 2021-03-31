# mso_schema_site_bd

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
module "mso_schema_site_bd" {
  source = "./modules/mso/d/mso_schema_site_bd"

  # bd_name - (required) is a type of string
  bd_name = null
  # host_route - (optional) is a type of bool
  host_route = null
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

variable "host_route" {
  description = "(optional)"
  type        = bool
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
data "mso_schema_site_bd" "this" {
  bd_name       = var.bd_name
  host_route    = var.host_route
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
  value       = data.mso_schema_site_bd.this.id
}

output "template_name" {
  description = "returns a string"
  value       = data.mso_schema_site_bd.this.template_name
}

output "this" {
  value = mso_schema_site_bd.this
}
```

[top](#index)