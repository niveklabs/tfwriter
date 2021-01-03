# fortios_system_geneve

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
module "fortios_system_geneve" {
  source = "./modules/fortios/r/fortios_system_geneve"

  # dstport - (optional) is a type of number
  dstport = null
  # interface - (required) is a type of string
  interface = null
  # ip_version - (required) is a type of string
  ip_version = null
  # name - (optional) is a type of string
  name = null
  # remote_ip - (required) is a type of string
  remote_ip = null
  # remote_ip6 - (optional) is a type of string
  remote_ip6 = null
  # vni - (required) is a type of number
  vni = null
}
```

[top](#index)

### Variables

```terraform
variable "dstport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ip_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_ip" {
  description = "(required)"
  type        = string
}

variable "remote_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vni" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_geneve" "this" {
  dstport    = var.dstport
  interface  = var.interface
  ip_version = var.ip_version
  name       = var.name
  remote_ip  = var.remote_ip
  remote_ip6 = var.remote_ip6
  vni        = var.vni
}
```

[top](#index)

### Outputs

```terraform
output "dstport" {
  description = "returns a number"
  value       = fortios_system_geneve.this.dstport
}

output "id" {
  description = "returns a string"
  value       = fortios_system_geneve.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_geneve.this.name
}

output "remote_ip6" {
  description = "returns a string"
  value       = fortios_system_geneve.this.remote_ip6
}

output "this" {
  value = fortios_system_geneve.this
}
```

[top](#index)