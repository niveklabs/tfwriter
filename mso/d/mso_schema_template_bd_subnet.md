# mso_schema_template_bd_subnet

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
module "mso_schema_template_bd_subnet" {
  source = "./modules/mso/d/mso_schema_template_bd_subnet"

  # bd_name - (required) is a type of string
  bd_name = null
  # description - (optional) is a type of string
  description = null
  # ip - (required) is a type of string
  ip = null
  # no_default_gateway - (optional) is a type of bool
  no_default_gateway = null
  # querier - (optional) is a type of bool
  querier = null
  # schema_id - (required) is a type of string
  schema_id = null
  # scope - (optional) is a type of string
  scope = null
  # shared - (optional) is a type of bool
  shared = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "no_default_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "querier" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_bd_subnet" "this" {
  # bd_name - (required) is a type of string
  bd_name = var.bd_name
  # description - (optional) is a type of string
  description = var.description
  # ip - (required) is a type of string
  ip = var.ip
  # no_default_gateway - (optional) is a type of bool
  no_default_gateway = var.no_default_gateway
  # querier - (optional) is a type of bool
  querier = var.querier
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # scope - (optional) is a type of string
  scope = var.scope
  # shared - (optional) is a type of bool
  shared = var.shared
  # template_name - (required) is a type of string
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.mso_schema_template_bd_subnet.this.description
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_bd_subnet.this.id
}

output "no_default_gateway" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd_subnet.this.no_default_gateway
}

output "querier" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd_subnet.this.querier
}

output "scope" {
  description = "returns a string"
  value       = data.mso_schema_template_bd_subnet.this.scope
}

output "shared" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd_subnet.this.shared
}

output "this" {
  value = mso_schema_template_bd_subnet.this
}
```

[top](#index)