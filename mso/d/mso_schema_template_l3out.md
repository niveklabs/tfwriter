# mso_schema_template_l3out

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
module "mso_schema_template_l3out" {
  source = "./modules/mso/d/mso_schema_template_l3out"

  # display_name - (optional) is a type of string
  display_name = null
  # l3out_name - (required) is a type of string
  l3out_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null
  # vrf_name - (optional) is a type of string
  vrf_name = null
  # vrf_schema_id - (optional) is a type of string
  vrf_schema_id = null
  # vrf_template_name - (optional) is a type of string
  vrf_template_name = null
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

variable "l3out_name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "vrf_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_l3out" "this" {
  display_name      = var.display_name
  l3out_name        = var.l3out_name
  schema_id         = var.schema_id
  template_name     = var.template_name
  vrf_name          = var.vrf_name
  vrf_schema_id     = var.vrf_schema_id
  vrf_template_name = var.vrf_template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_l3out.this.id
}

output "vrf_schema_id" {
  description = "returns a string"
  value       = data.mso_schema_template_l3out.this.vrf_schema_id
}

output "vrf_template_name" {
  description = "returns a string"
  value       = data.mso_schema_template_l3out.this.vrf_template_name
}

output "this" {
  value = mso_schema_template_l3out.this
}
```

[top](#index)