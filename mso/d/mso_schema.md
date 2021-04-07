# mso_schema

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
module "mso_schema" {
  source = "./modules/mso/d/mso_schema"

  # name - (required) is a type of string
  name = null
  # template_name - (optional) is a type of string
  template_name = null
  # tenant_id - (optional) is a type of string
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
  description = "(optional)"
  type        = string
  default     = null
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
data "mso_schema" "this" {
  # name - (required) is a type of string
  name = var.name
  # template_name - (optional) is a type of string
  template_name = var.template_name
  # tenant_id - (optional) is a type of string
  tenant_id = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema.this.id
}

output "this" {
  value = mso_schema.this
}
```

[top](#index)