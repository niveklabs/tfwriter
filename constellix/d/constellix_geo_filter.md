# constellix_geo_filter

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
module "constellix_geo_filter" {
  source = "./modules/constellix/d/constellix_geo_filter"

  # asn - (optional) is a type of list of number
  asn = []
  # filterruleslimit - (optional) is a type of number
  filterruleslimit = null
  # geoipcontinents - (optional) is a type of list of string
  geoipcontinents = []
  # geoipcountries - (optional) is a type of list of string
  geoipcountries = []
  # geoipregions - (optional) is a type of list of string
  geoipregions = []
  # ipv4 - (optional) is a type of list of string
  ipv4 = []
  # ipv6 - (optional) is a type of list of string
  ipv6 = []
  # name - (required) is a type of string
  name = null
  # regions - (optional) is a type of map of string
  regions = {}
}
```

[top](#index)

### Variables

```terraform
variable "asn" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "filterruleslimit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "geoipcontinents" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "geoipcountries" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "geoipregions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ipv4" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "regions" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "constellix_geo_filter" "this" {
  asn              = var.asn
  filterruleslimit = var.filterruleslimit
  geoipcontinents  = var.geoipcontinents
  geoipcountries   = var.geoipcountries
  geoipregions     = var.geoipregions
  ipv4             = var.ipv4
  ipv6             = var.ipv6
  name             = var.name
  regions          = var.regions
}
```

[top](#index)

### Outputs

```terraform
output "asn" {
  description = "returns a list of number"
  value       = data.constellix_geo_filter.this.asn
}

output "filterruleslimit" {
  description = "returns a number"
  value       = data.constellix_geo_filter.this.filterruleslimit
}

output "geoipcontinents" {
  description = "returns a list of string"
  value       = data.constellix_geo_filter.this.geoipcontinents
}

output "geoipcountries" {
  description = "returns a list of string"
  value       = data.constellix_geo_filter.this.geoipcountries
}

output "geoipregions" {
  description = "returns a list of string"
  value       = data.constellix_geo_filter.this.geoipregions
}

output "id" {
  description = "returns a string"
  value       = data.constellix_geo_filter.this.id
}

output "ipv4" {
  description = "returns a list of string"
  value       = data.constellix_geo_filter.this.ipv4
}

output "ipv6" {
  description = "returns a list of string"
  value       = data.constellix_geo_filter.this.ipv6
}

output "regions" {
  description = "returns a map of string"
  value       = data.constellix_geo_filter.this.regions
}

output "this" {
  value = constellix_geo_filter.this
}
```

[top](#index)