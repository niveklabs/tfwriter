# fortios_system_ipiptunnel

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
module "fortios_system_ipiptunnel" {
  source = "./modules/fortios/r/fortios_system_ipiptunnel"

  # interface - (required) is a type of string
  interface = null
  # local_gw - (required) is a type of string
  local_gw = null
  # name - (optional) is a type of string
  name = null
  # remote_gw - (required) is a type of string
  remote_gw = null
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}

variable "local_gw" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_gw" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ipiptunnel" "this" {
  interface = var.interface
  local_gw  = var.local_gw
  name      = var.name
  remote_gw = var.remote_gw
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ipiptunnel.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_ipiptunnel.this.name
}

output "this" {
  value = fortios_system_ipiptunnel.this
}
```

[top](#index)