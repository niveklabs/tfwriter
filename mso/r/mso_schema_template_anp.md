# mso_schema_template_anp

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
module "mso_schema_template_anp" {
  source = "./modules/mso/r/mso_schema_template_anp"

  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template - (required) is a type of string
  template = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_anp" "this" {
  display_name = var.display_name
  name         = var.name
  schema_id    = var.schema_id
  template     = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_template_anp.this.id
}

output "this" {
  value = mso_schema_template_anp.this
}
```

[top](#index)