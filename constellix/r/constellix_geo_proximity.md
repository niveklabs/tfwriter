# constellix_geo_proximity

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
module "constellix_geo_proximity" {
  source = "./modules/constellix/r/constellix_geo_proximity"

  # city - (optional) is a type of number
  city = null
  # country - (optional) is a type of string
  country = null
  # latitude - (optional) is a type of number
  latitude = null
  # longitude - (optional) is a type of number
  longitude = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "city" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "country" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "latitude" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "longitude" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "constellix_geo_proximity" "this" {
  # city - (optional) is a type of number
  city = var.city
  # country - (optional) is a type of string
  country = var.country
  # latitude - (optional) is a type of number
  latitude = var.latitude
  # longitude - (optional) is a type of number
  longitude = var.longitude
  # name - (optional) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "city" {
  description = "returns a number"
  value       = constellix_geo_proximity.this.city
}

output "country" {
  description = "returns a string"
  value       = constellix_geo_proximity.this.country
}

output "id" {
  description = "returns a string"
  value       = constellix_geo_proximity.this.id
}

output "latitude" {
  description = "returns a number"
  value       = constellix_geo_proximity.this.latitude
}

output "longitude" {
  description = "returns a number"
  value       = constellix_geo_proximity.this.longitude
}

output "name" {
  description = "returns a string"
  value       = constellix_geo_proximity.this.name
}

output "region" {
  description = "returns a string"
  value       = constellix_geo_proximity.this.region
}

output "this" {
  value = constellix_geo_proximity.this
}
```

[top](#index)