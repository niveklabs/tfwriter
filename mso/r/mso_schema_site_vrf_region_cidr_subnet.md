# mso_schema_site_vrf_region_cidr_subnet

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
module "mso_schema_site_vrf_region_cidr_subnet" {
  source = "./modules/mso/r/mso_schema_site_vrf_region_cidr_subnet"

  # cidr_ip - (required) is a type of string
  cidr_ip = null
  # ip - (required) is a type of string
  ip = null
  # region_name - (required) is a type of string
  region_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
  # usage - (optional) is a type of string
  usage = null
  # vrf_name - (required) is a type of string
  vrf_name = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_ip" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(required)"
  type        = string
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

variable "usage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_name" {
  description = "(required)"
  type        = string
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_site_vrf_region_cidr_subnet" "this" {
  cidr_ip       = var.cidr_ip
  ip            = var.ip
  region_name   = var.region_name
  schema_id     = var.schema_id
  site_id       = var.site_id
  template_name = var.template_name
  usage         = var.usage
  vrf_name      = var.vrf_name
  zone          = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_site_vrf_region_cidr_subnet.this.id
}

output "this" {
  value = mso_schema_site_vrf_region_cidr_subnet.this
}
```

[top](#index)