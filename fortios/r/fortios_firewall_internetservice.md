# fortios_firewall_internetservice

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
module "fortios_firewall_internetservice" {
  source = "./modules/fortios/r/fortios_firewall_internetservice"

  # database - (optional) is a type of string
  database = null
  # direction - (optional) is a type of string
  direction = null
  # extra_ip_range_number - (optional) is a type of number
  extra_ip_range_number = null
  # fosid - (optional) is a type of number
  fosid = null
  # icon_id - (optional) is a type of number
  icon_id = null
  # ip_number - (optional) is a type of number
  ip_number = null
  # ip_range_number - (optional) is a type of number
  ip_range_number = null
  # name - (optional) is a type of string
  name = null
  # obsolete - (optional) is a type of number
  obsolete = null
  # reputation - (optional) is a type of number
  reputation = null
  # singularity - (optional) is a type of number
  singularity = null
  # sld_id - (optional) is a type of number
  sld_id = null
}
```

[top](#index)

### Variables

```terraform
variable "database" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extra_ip_range_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icon_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_range_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obsolete" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reputation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "singularity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sld_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetservice" "this" {
  database              = var.database
  direction             = var.direction
  extra_ip_range_number = var.extra_ip_range_number
  fosid                 = var.fosid
  icon_id               = var.icon_id
  ip_number             = var.ip_number
  ip_range_number       = var.ip_range_number
  name                  = var.name
  obsolete              = var.obsolete
  reputation            = var.reputation
  singularity           = var.singularity
  sld_id                = var.sld_id
}
```

[top](#index)

### Outputs

```terraform
output "database" {
  description = "returns a string"
  value       = fortios_firewall_internetservice.this.database
}

output "direction" {
  description = "returns a string"
  value       = fortios_firewall_internetservice.this.direction
}

output "extra_ip_range_number" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.extra_ip_range_number
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.fosid
}

output "icon_id" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.icon_id
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservice.this.id
}

output "ip_number" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.ip_number
}

output "ip_range_number" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.ip_range_number
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetservice.this.name
}

output "obsolete" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.obsolete
}

output "reputation" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.reputation
}

output "singularity" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.singularity
}

output "sld_id" {
  description = "returns a number"
  value       = fortios_firewall_internetservice.this.sld_id
}

output "this" {
  value = fortios_firewall_internetservice.this
}
```

[top](#index)