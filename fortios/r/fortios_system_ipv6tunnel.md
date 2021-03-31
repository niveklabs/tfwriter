# fortios_system_ipv6tunnel

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
module "fortios_system_ipv6tunnel" {
  source = null

  # destination - (required) is a type of string
  destination = null
  # interface - (optional) is a type of string
  interface = null
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
resource "fortios_system_ipv6tunnel" "this" {
  destination = var.destination
  interface   = var.interface
  name        = var.name
  source      = var.source
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ipv6tunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_ipv6tunnel.this.interface
}

output "name" {
  description = "returns a string"
  value       = fortios_system_ipv6tunnel.this.name
}

output "source" {
  description = "returns a string"
  value       = fortios_system_ipv6tunnel.this.source
}

output "this" {
  value = fortios_system_ipv6tunnel.this
}
```

[top](#index)