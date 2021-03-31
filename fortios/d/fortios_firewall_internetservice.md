# fortios_firewall_internetservice

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_firewall_internetservice"

  # fosid - (required) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_firewall_internetservice" "this" {
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "database" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservice.this.database
}

output "direction" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservice.this.direction
}

output "extra_ip_range_number" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.extra_ip_range_number
}

output "icon_id" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.icon_id
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservice.this.id
}

output "ip_number" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.ip_number
}

output "ip_range_number" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.ip_range_number
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservice.this.name
}

output "obsolete" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.obsolete
}

output "reputation" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.reputation
}

output "singularity" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.singularity
}

output "sld_id" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservice.this.sld_id
}

output "this" {
  value = fortios_firewall_internetservice.this
}
```

[top](#index)