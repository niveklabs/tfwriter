# constellix_domain

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
module "constellix_domain" {
  source = "./modules/constellix/r/constellix_domain"

  # has_geoip - (optional) is a type of bool
  has_geoip = null
  # has_gtd_regions - (optional) is a type of bool
  has_gtd_regions = null
  # name - (required) is a type of string
  name = null
  # nameserver_group - (optional) is a type of string
  nameserver_group = null
  # note - (optional) is a type of string
  note = null
  # soa - (optional) is a type of map of string
  soa = {}
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
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

variable "nameserver_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "soa" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "constellix_domain" "this" {
  # has_geoip - (optional) is a type of bool
  has_geoip = var.has_geoip
  # has_gtd_regions - (optional) is a type of bool
  has_gtd_regions = var.has_gtd_regions
  # name - (required) is a type of string
  name = var.name
  # nameserver_group - (optional) is a type of string
  nameserver_group = var.nameserver_group
  # note - (optional) is a type of string
  note = var.note
  # soa - (optional) is a type of map of string
  soa = var.soa
  # tags - (optional) is a type of list of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "has_geoip" {
  description = "returns a bool"
  value       = constellix_domain.this.has_geoip
}

output "has_gtd_regions" {
  description = "returns a bool"
  value       = constellix_domain.this.has_gtd_regions
}

output "id" {
  description = "returns a string"
  value       = constellix_domain.this.id
}

output "nameserver_group" {
  description = "returns a string"
  value       = constellix_domain.this.nameserver_group
}

output "note" {
  description = "returns a string"
  value       = constellix_domain.this.note
}

output "soa" {
  description = "returns a map of string"
  value       = constellix_domain.this.soa
}

output "this" {
  value = constellix_domain.this
}
```

[top](#index)