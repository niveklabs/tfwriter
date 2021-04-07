# constellix_geo_filter

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_geo_filter" {
  source = "./modules/constellix/r/constellix_geo_filter"

  # asn - (optional) is a type of list of number
  asn = []
  # filter_rules_limit - (optional) is a type of number
  filter_rules_limit = null
  # geoip_continents - (required) is a type of list of string
  geoip_continents = []
  # geoip_countries - (optional) is a type of list of string
  geoip_countries = []
  # geoip_regions - (optional) is a type of list of string
  geoip_regions = []
  # ipv4 - (optional) is a type of list of string
  ipv4 = []
  # ipv6 - (optional) is a type of list of string
  ipv6 = []
  # name - (required) is a type of string
  name = null
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

variable "filter_rules_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "geoip_continents" {
  description = "(required)"
  type        = list(string)
}

variable "geoip_countries" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "geoip_regions" {
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
```

[top](#index)

### Resource

```terraform
resource "constellix_geo_filter" "this" {
  # asn - (optional) is a type of list of number
  asn = var.asn
  # filter_rules_limit - (optional) is a type of number
  filter_rules_limit = var.filter_rules_limit
  # geoip_continents - (required) is a type of list of string
  geoip_continents = var.geoip_continents
  # geoip_countries - (optional) is a type of list of string
  geoip_countries = var.geoip_countries
  # geoip_regions - (optional) is a type of list of string
  geoip_regions = var.geoip_regions
  # ipv4 - (optional) is a type of list of string
  ipv4 = var.ipv4
  # ipv6 - (optional) is a type of list of string
  ipv6 = var.ipv6
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "asn" {
  description = "returns a list of number"
  value       = constellix_geo_filter.this.asn
}

output "filter_rules_limit" {
  description = "returns a number"
  value       = constellix_geo_filter.this.filter_rules_limit
}

output "geoip_countries" {
  description = "returns a list of string"
  value       = constellix_geo_filter.this.geoip_countries
}

output "geoip_regions" {
  description = "returns a list of string"
  value       = constellix_geo_filter.this.geoip_regions
}

output "id" {
  description = "returns a string"
  value       = constellix_geo_filter.this.id
}

output "ipv4" {
  description = "returns a list of string"
  value       = constellix_geo_filter.this.ipv4
}

output "ipv6" {
  description = "returns a list of string"
  value       = constellix_geo_filter.this.ipv6
}

output "this" {
  value = constellix_geo_filter.this
}
```

[top](#index)