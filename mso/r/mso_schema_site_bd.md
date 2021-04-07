# mso_schema_site_bd

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
module "mso_schema_site_bd" {
  source = "./modules/mso/r/mso_schema_site_bd"

  # bd_name - (required) is a type of string
  bd_name = null
  # host_route - (optional) is a type of bool
  host_route = null
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
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_site_bd" "this" {
  # bd_name - (required) is a type of string
  bd_name = var.bd_name
  # host_route - (optional) is a type of bool
  host_route = var.host_route
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
  value       = mso_schema_site_bd.this.id
}

output "this" {
  value = mso_schema_site_bd.this
}
```

[top](#index)