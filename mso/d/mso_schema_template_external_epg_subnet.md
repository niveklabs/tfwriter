# mso_schema_template_external_epg_subnet

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
module "mso_schema_template_external_epg_subnet" {
  source = "./modules/mso/d/mso_schema_template_external_epg_subnet"

  # aggregate - (optional) is a type of list of string
  aggregate = []
  # external_epg_name - (required) is a type of string
  external_epg_name = null
  # ip - (required) is a type of string
  ip = null
  # name - (optional) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # scope - (optional) is a type of list of string
  scope = []
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "aggregate" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "external_epg_name" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_external_epg_subnet" "this" {
  aggregate         = var.aggregate
  external_epg_name = var.external_epg_name
  ip                = var.ip
  name              = var.name
  schema_id         = var.schema_id
  scope             = var.scope
  template_name     = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "aggregate" {
  description = "returns a list of string"
  value       = data.mso_schema_template_external_epg_subnet.this.aggregate
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_external_epg_subnet.this.id
}

output "scope" {
  description = "returns a list of string"
  value       = data.mso_schema_template_external_epg_subnet.this.scope
}

output "this" {
  value = mso_schema_template_external_epg_subnet.this
}
```

[top](#index)