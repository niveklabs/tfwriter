# fortios_firewall_internetservicedefinition

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
module "fortios_firewall_internetservicedefinition" {
  source = "./modules/fortios/d/fortios_firewall_internetservicedefinition"

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
data "fortios_firewall_internetservicedefinition" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "entry" {
  description = "returns a list of object"
  value       = data.fortios_firewall_internetservicedefinition.this.entry
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_internetservicedefinition.this.id
}

output "this" {
  value = fortios_firewall_internetservicedefinition.this
}
```

[top](#index)