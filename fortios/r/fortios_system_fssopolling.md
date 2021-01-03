# fortios_system_fssopolling

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
module "fortios_system_fssopolling" {
  source = "./modules/fortios/r/fortios_system_fssopolling"

  # auth_password - (optional) is a type of string
  auth_password = null
  # authentication - (optional) is a type of string
  authentication = null
  # listening_port - (optional) is a type of number
  listening_port = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listening_port" {
  description = "(optional)"
  type        = number
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
resource "fortios_system_fssopolling" "this" {
  auth_password  = var.auth_password
  authentication = var.authentication
  listening_port = var.listening_port
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "authentication" {
  description = "returns a string"
  value       = fortios_system_fssopolling.this.authentication
}

output "id" {
  description = "returns a string"
  value       = fortios_system_fssopolling.this.id
}

output "listening_port" {
  description = "returns a number"
  value       = fortios_system_fssopolling.this.listening_port
}

output "status" {
  description = "returns a string"
  value       = fortios_system_fssopolling.this.status
}

output "this" {
  value = fortios_system_fssopolling.this
}
```

[top](#index)