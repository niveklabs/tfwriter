# mso_schema_template_anp_epg_subnet

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
module "mso_schema_template_anp_epg_subnet" {
  source = "./modules/mso/r/mso_schema_template_anp_epg_subnet"

  # anp_name - (required) is a type of string
  anp_name = null
  # epg_name - (required) is a type of string
  epg_name = null
  # ip - (required) is a type of string
  ip = null
  # schema_id - (required) is a type of string
  schema_id = null
  # scope - (optional) is a type of string
  scope = null
  # shared - (optional) is a type of bool
  shared = null
  # template - (required) is a type of string
  template = null
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

variable "ip" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_anp_epg_subnet" "this" {
  anp_name  = var.anp_name
  epg_name  = var.epg_name
  ip        = var.ip
  schema_id = var.schema_id
  scope     = var.scope
  shared    = var.shared
  template  = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_template_anp_epg_subnet.this.id
}

output "this" {
  value = mso_schema_template_anp_epg_subnet.this
}
```

[top](#index)