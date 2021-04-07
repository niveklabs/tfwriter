# fortios_system_macaddresstable

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
module "fortios_system_macaddresstable" {
  source = "./modules/fortios/r/fortios_system_macaddresstable"

  # interface - (required) is a type of string
  interface = null
  # mac - (required) is a type of string
  mac = null
  # reply_substitute - (optional) is a type of string
  reply_substitute = null
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}

variable "mac" {
  description = "(required)"
  type        = string
}

variable "reply_substitute" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_macaddresstable" "this" {
  # interface - (required) is a type of string
  interface = var.interface
  # mac - (required) is a type of string
  mac = var.mac
  # reply_substitute - (optional) is a type of string
  reply_substitute = var.reply_substitute
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_macaddresstable.this.id
}

output "reply_substitute" {
  description = "returns a string"
  value       = fortios_system_macaddresstable.this.reply_substitute
}

output "this" {
  value = fortios_system_macaddresstable.this
}
```

[top](#index)