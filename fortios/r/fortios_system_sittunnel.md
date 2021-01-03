# fortios_system_sittunnel

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_sittunnel" {
  source = null

  # destination - (required) is a type of string
  destination = null
  # interface - (optional) is a type of string
  interface = null
  # ip6 - (optional) is a type of string
  ip6 = null
  # name - (optional) is a type of string
  name = null
  # source - (optional) is a type of string
}
```

[top](#index)

### Variables

```terraform
variable "destination" {
  description = "(required)"
  type        = string
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_sittunnel" "this" {
  destination = var.destination
  interface   = var.interface
  ip6         = var.ip6
  name        = var.name
  source      = var.source
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_sittunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_sittunnel.this.interface
}

output "ip6" {
  description = "returns a string"
  value       = fortios_system_sittunnel.this.ip6
}

output "name" {
  description = "returns a string"
  value       = fortios_system_sittunnel.this.name
}

output "source" {
  description = "returns a string"
  value       = fortios_system_sittunnel.this.source
}

output "this" {
  value = fortios_system_sittunnel.this
}
```

[top](#index)