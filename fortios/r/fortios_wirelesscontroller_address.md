# fortios_wirelesscontroller_address

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
module "fortios_wirelesscontroller_address" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_address"

  # fosid - (optional) is a type of string
  fosid = null
  # mac - (optional) is a type of string
  mac = null
  # policy - (optional) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_address" "this" {
  fosid  = var.fosid
  mac    = var.mac
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_address.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_address.this.id
}

output "mac" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_address.this.mac
}

output "policy" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_address.this.policy
}

output "this" {
  value = fortios_wirelesscontroller_address.this
}
```

[top](#index)