# mso_schema_site_vrf_region_cidr

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
module "mso_schema_site_vrf_region_cidr" {
  source = "./modules/mso/r/mso_schema_site_vrf_region_cidr"

  # ip - (required) is a type of string
  ip = null
  # primary - (required) is a type of bool
  primary = null
  # region_name - (required) is a type of string
  region_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
  # vrf_name - (required) is a type of string
  vrf_name = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required)"
  type        = string
}

variable "primary" {
  description = "(required)"
  type        = bool
}

variable "region_name" {
  description = "(required)"
  type        = string
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

variable "vrf_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_site_vrf_region_cidr" "this" {
  # ip - (required) is a type of string
  ip = var.ip
  # primary - (required) is a type of bool
  primary = var.primary
  # region_name - (required) is a type of string
  region_name = var.region_name
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # site_id - (required) is a type of string
  site_id = var.site_id
  # template_name - (required) is a type of string
  template_name = var.template_name
  # vrf_name - (required) is a type of string
  vrf_name = var.vrf_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_site_vrf_region_cidr.this.id
}

output "this" {
  value = mso_schema_site_vrf_region_cidr.this
}
```

[top](#index)