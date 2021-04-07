# fortios_firewall_internetservicename

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_internetservicename" {
  source = "./modules/fortios/r/fortios_firewall_internetservicename"

  # city_id - (optional) is a type of number
  city_id = null
  # country_id - (optional) is a type of number
  country_id = null
  # internet_service_id - (optional) is a type of number
  internet_service_id = null
  # name - (optional) is a type of string
  name = null
  # region_id - (optional) is a type of number
  region_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "city_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "country_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internet_service_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetservicename" "this" {
  # city_id - (optional) is a type of number
  city_id = var.city_id
  # country_id - (optional) is a type of number
  country_id = var.country_id
  # internet_service_id - (optional) is a type of number
  internet_service_id = var.internet_service_id
  # name - (optional) is a type of string
  name = var.name
  # region_id - (optional) is a type of number
  region_id = var.region_id
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "city_id" {
  description = "returns a number"
  value       = fortios_firewall_internetservicename.this.city_id
}

output "country_id" {
  description = "returns a number"
  value       = fortios_firewall_internetservicename.this.country_id
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservicename.this.id
}

output "internet_service_id" {
  description = "returns a number"
  value       = fortios_firewall_internetservicename.this.internet_service_id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetservicename.this.name
}

output "region_id" {
  description = "returns a number"
  value       = fortios_firewall_internetservicename.this.region_id
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_internetservicename.this.type
}

output "this" {
  value = fortios_firewall_internetservicename.this
}
```

[top](#index)