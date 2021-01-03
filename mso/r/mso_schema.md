# mso_schema

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
module "mso_schema" {
  source = "./modules/mso/r/mso_schema"

  # name - (required) is a type of string
  name = null
  # template_name - (required) is a type of string
  template_name = null
  # tenant_id - (required) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema" "this" {
  name          = var.name
  template_name = var.template_name
  tenant_id     = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema.this.id
}

output "this" {
  value = mso_schema.this
}
```

[top](#index)