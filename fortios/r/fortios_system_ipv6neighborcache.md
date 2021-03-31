# fortios_system_ipv6neighborcache

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
module "fortios_system_ipv6neighborcache" {
  source = "./modules/fortios/r/fortios_system_ipv6neighborcache"

  # fosid - (required) is a type of number
  fosid = null
  # interface - (required) is a type of string
  interface = null
  # ipv6 - (required) is a type of string
  ipv6 = null
  # mac - (required) is a type of string
  mac = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(required)"
  type        = number
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ipv6" {
  description = "(required)"
  type        = string
}

variable "mac" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ipv6neighborcache" "this" {
  fosid     = var.fosid
  interface = var.interface
  ipv6      = var.ipv6
  mac       = var.mac
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ipv6neighborcache.this.id
}

output "this" {
  value = fortios_system_ipv6neighborcache.this
}
```

[top](#index)