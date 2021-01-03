# fortios_system_fortisandbox

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
module "fortios_system_fortisandbox" {
  source = "./modules/fortios/r/fortios_system_fortisandbox"

  # email - (optional) is a type of string
  email = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enc_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_fortisandbox" "this" {
  email                 = var.email
  enc_algorithm         = var.enc_algorithm
  server                = var.server
  source_ip             = var.source_ip
  ssl_min_proto_version = var.ssl_min_proto_version
  status                = var.status
}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.email
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.enc_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.id
}

output "server" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_system_fortisandbox.this.status
}

output "this" {
  value = fortios_system_fortisandbox.this
}
```

[top](#index)