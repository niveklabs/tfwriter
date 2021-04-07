# fortios_firewall_internetservicecustom

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
module "fortios_firewall_internetservicecustom" {
  source = "./modules/fortios/d/fortios_firewall_internetservicecustom"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_firewall_internetservicecustom" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservicecustom.this.comment
}

output "entry" {
  description = "returns a list of object"
  value       = data.fortios_firewall_internetservicecustom.this.entry
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservicecustom.this.id
}

output "reputation" {
  description = "returns a number"
  value       = data.fortios_firewall_internetservicecustom.this.reputation
}

output "this" {
  value = fortios_firewall_internetservicecustom.this
}
```

[top](#index)