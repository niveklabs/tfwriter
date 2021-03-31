# fortios_webproxy_wisp

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
module "fortios_webproxy_wisp" {
  source = "./modules/fortios/r/fortios_webproxy_wisp"

  # comment - (optional) is a type of string
  comment = null
  # max_connections - (optional) is a type of number
  max_connections = null
  # name - (required) is a type of string
  name = null
  # outgoing_ip - (optional) is a type of string
  outgoing_ip = null
  # server_ip - (required) is a type of string
  server_ip = null
  # server_port - (required) is a type of number
  server_port = null
  # timeout - (optional) is a type of number
  timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
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
  description = "(required)"
  type        = string
}

variable "outgoing_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_ip" {
  description = "(required)"
  type        = string
}

variable "server_port" {
  description = "(required)"
  type        = number
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webproxy_wisp" "this" {
  comment         = var.comment
  max_connections = var.max_connections
  name            = var.name
  outgoing_ip     = var.outgoing_ip
  server_ip       = var.server_ip
  server_port     = var.server_port
  timeout         = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_webproxy_wisp.this.id
}

output "max_connections" {
  description = "returns a number"
  value       = fortios_webproxy_wisp.this.max_connections
}

output "outgoing_ip" {
  description = "returns a string"
  value       = fortios_webproxy_wisp.this.outgoing_ip
}

output "timeout" {
  description = "returns a number"
  value       = fortios_webproxy_wisp.this.timeout
}

output "this" {
  value = fortios_webproxy_wisp.this
}
```

[top](#index)