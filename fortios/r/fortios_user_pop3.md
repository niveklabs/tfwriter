# fortios_user_pop3

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
module "fortios_user_pop3" {
  source = "./modules/fortios/r/fortios_user_pop3"

  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # secure - (optional) is a type of string
  secure = null
  # server - (required) is a type of string
  server = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
}
```

[top](#index)

### Variables

```terraform
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

variable "secure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(required)"
  type        = string
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_pop3" "this" {
  # name - (optional) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # secure - (optional) is a type of string
  secure = var.secure
  # server - (required) is a type of string
  server = var.server
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = var.ssl_min_proto_version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_user_pop3.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_user_pop3.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_user_pop3.this.port
}

output "secure" {
  description = "returns a string"
  value       = fortios_user_pop3.this.secure
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_user_pop3.this.ssl_min_proto_version
}

output "this" {
  value = fortios_user_pop3.this
}
```

[top](#index)