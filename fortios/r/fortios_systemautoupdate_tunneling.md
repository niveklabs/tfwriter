# fortios_systemautoupdate_tunneling

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
module "fortios_systemautoupdate_tunneling" {
  source = "./modules/fortios/r/fortios_systemautoupdate_tunneling"

  # address - (optional) is a type of string
  address = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # status - (optional) is a type of string
  status = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemautoupdate_tunneling" "this" {
  address  = var.address
  password = var.password
  port     = var.port
  status   = var.status
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = fortios_systemautoupdate_tunneling.this.address
}

output "id" {
  description = "returns a string"
  value       = fortios_systemautoupdate_tunneling.this.id
}

output "port" {
  description = "returns a number"
  value       = fortios_systemautoupdate_tunneling.this.port
}

output "status" {
  description = "returns a string"
  value       = fortios_systemautoupdate_tunneling.this.status
}

output "username" {
  description = "returns a string"
  value       = fortios_systemautoupdate_tunneling.this.username
}

output "this" {
  value = fortios_systemautoupdate_tunneling.this
}
```

[top](#index)