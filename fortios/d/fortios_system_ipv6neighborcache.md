# fortios_system_ipv6neighborcache

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
module "fortios_system_ipv6neighborcache" {
  source = "./modules/fortios/d/fortios_system_ipv6neighborcache"

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
data "fortios_system_ipv6neighborcache" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_ipv6neighborcache.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_ipv6neighborcache.this.interface
}

output "ipv6" {
  description = "returns a string"
  value       = data.fortios_system_ipv6neighborcache.this.ipv6
}

output "mac" {
  description = "returns a string"
  value       = data.fortios_system_ipv6neighborcache.this.mac
}

output "this" {
  value = fortios_system_ipv6neighborcache.this
}
```

[top](#index)