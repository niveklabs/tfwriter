# fortios_system_arptable

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
module "fortios_system_arptable" {
  source = "./modules/fortios/r/fortios_system_arptable"

  # fosid - (required) is a type of number
  fosid = null
  # interface - (required) is a type of string
  interface = null
  # ip - (required) is a type of string
  ip = null
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

variable "ip" {
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
resource "fortios_system_arptable" "this" {
  fosid     = var.fosid
  interface = var.interface
  ip        = var.ip
  mac       = var.mac
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_arptable.this.id
}

output "this" {
  value = fortios_system_arptable.this
}
```

[top](#index)