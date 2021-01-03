# mso_schema_template

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
module "mso_schema_template" {
  source = "./modules/mso/d/mso_schema_template"

  # display_name - (optional) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
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

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template" "this" {
  display_name = var.display_name
  name         = var.name
  schema_id    = var.schema_id
  tenant_id    = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template.this.id
}

output "this" {
  value = mso_schema_template.this
}
```

[top](#index)