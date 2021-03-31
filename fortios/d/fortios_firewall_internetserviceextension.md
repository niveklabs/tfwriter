# fortios_firewall_internetserviceextension

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
module "fortios_firewall_internetserviceextension" {
  source = "./modules/fortios/d/fortios_firewall_internetserviceextension"

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
data "fortios_firewall_internetserviceextension" "this" {
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_internetserviceextension.this.comment
}

output "disable_entry" {
  description = "returns a list of object"
  value       = data.fortios_firewall_internetserviceextension.this.disable_entry
}

output "entry" {
  description = "returns a list of object"
  value       = data.fortios_firewall_internetserviceextension.this.entry
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_internetserviceextension.this.id
}

output "this" {
  value = fortios_firewall_internetserviceextension.this
}
```

[top](#index)