# fortios_system_proberesponse

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
module "fortios_system_proberesponse" {
  source = "./modules/fortios/r/fortios_system_proberesponse"

  # http_probe_value - (optional) is a type of string
  http_probe_value = null
  # mode - (optional) is a type of string
  mode = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # security_mode - (optional) is a type of string
  security_mode = null
  # timeout - (optional) is a type of number
  timeout = null
  # ttl_mode - (optional) is a type of string
  ttl_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "http_probe_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ttl_mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_proberesponse" "this" {
  http_probe_value = var.http_probe_value
  mode             = var.mode
  password         = var.password
  port             = var.port
  security_mode    = var.security_mode
  timeout          = var.timeout
  ttl_mode         = var.ttl_mode
}
```

[top](#index)

### Outputs

```terraform
output "http_probe_value" {
  description = "returns a string"
  value       = fortios_system_proberesponse.this.http_probe_value
}

output "id" {
  description = "returns a string"
  value       = fortios_system_proberesponse.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_proberesponse.this.mode
}

output "port" {
  description = "returns a number"
  value       = fortios_system_proberesponse.this.port
}

output "security_mode" {
  description = "returns a string"
  value       = fortios_system_proberesponse.this.security_mode
}

output "timeout" {
  description = "returns a number"
  value       = fortios_system_proberesponse.this.timeout
}

output "ttl_mode" {
  description = "returns a string"
  value       = fortios_system_proberesponse.this.ttl_mode
}

output "this" {
  value = fortios_system_proberesponse.this
}
```

[top](#index)