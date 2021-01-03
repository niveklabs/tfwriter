# fortios_icap_server

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
module "fortios_icap_server" {
  source = "./modules/fortios/r/fortios_icap_server"

  # ip6_address - (optional) is a type of string
  ip6_address = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # max_connections - (optional) is a type of number
  max_connections = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
}
```

[top](#index)

### Variables

```terraform
variable "ip6_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_connections" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_icap_server" "this" {
  ip6_address     = var.ip6_address
  ip_address      = var.ip_address
  ip_version      = var.ip_version
  max_connections = var.max_connections
  name            = var.name
  port            = var.port
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_icap_server.this.id
}

output "ip6_address" {
  description = "returns a string"
  value       = fortios_icap_server.this.ip6_address
}

output "ip_address" {
  description = "returns a string"
  value       = fortios_icap_server.this.ip_address
}

output "ip_version" {
  description = "returns a string"
  value       = fortios_icap_server.this.ip_version
}

output "max_connections" {
  description = "returns a number"
  value       = fortios_icap_server.this.max_connections
}

output "name" {
  description = "returns a string"
  value       = fortios_icap_server.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_icap_server.this.port
}

output "this" {
  value = fortios_icap_server.this
}
```

[top](#index)