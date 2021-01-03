# constellix_template

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_template" {
  source = "./modules/constellix/d/constellix_template"

  # domain - (optional) is a type of number
  domain = null
  # has_geoip - (optional) is a type of bool
  has_geoip = null
  # has_gtd_regions - (optional) is a type of bool
  has_gtd_regions = null
  # name - (required) is a type of string
  name = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "has_geoip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "has_gtd_regions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "constellix_template" "this" {
  domain          = var.domain
  has_geoip       = var.has_geoip
  has_gtd_regions = var.has_gtd_regions
  name            = var.name
  version         = var.version
}
```

[top](#index)

### Outputs

```terraform
output "domain" {
  description = "returns a number"
  value       = data.constellix_template.this.domain
}

output "has_geoip" {
  description = "returns a bool"
  value       = data.constellix_template.this.has_geoip
}

output "has_gtd_regions" {
  description = "returns a bool"
  value       = data.constellix_template.this.has_gtd_regions
}

output "id" {
  description = "returns a string"
  value       = data.constellix_template.this.id
}

output "version" {
  description = "returns a number"
  value       = data.constellix_template.this.version
}

output "this" {
  value = constellix_template.this
}
```

[top](#index)