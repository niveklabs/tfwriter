# mso_schema_site

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
module "mso_schema_site" {
  source = "./modules/mso/r/mso_schema_site"

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
resource "mso_schema_site" "this" {
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
  value       = mso_schema_site.this.id
}

output "this" {
  value = mso_schema_site.this
}
```

[top](#index)