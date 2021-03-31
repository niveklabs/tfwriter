# fortios_switchcontroller_stpsettings

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
module "fortios_switchcontroller_stpsettings" {
  source = "./modules/fortios/r/fortios_switchcontroller_stpsettings"

  # forward_time - (optional) is a type of number
  forward_time = null
  # hello_time - (optional) is a type of number
  hello_time = null
  # max_age - (optional) is a type of number
  max_age = null
  # max_hops - (optional) is a type of number
  max_hops = null
  # name - (optional) is a type of string
  name = null
  # pending_timer - (optional) is a type of number
  pending_timer = null
  # revision - (optional) is a type of number
  revision = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "forward_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hello_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_hops" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pending_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "revision" {
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
resource "fortios_switchcontroller_stpsettings" "this" {
  forward_time  = var.forward_time
  hello_time    = var.hello_time
  max_age       = var.max_age
  max_hops      = var.max_hops
  name          = var.name
  pending_timer = var.pending_timer
  revision      = var.revision
  status        = var.status
}
```

[top](#index)

### Outputs

```terraform
output "forward_time" {
  description = "returns a number"
  value       = fortios_switchcontroller_stpsettings.this.forward_time
}

output "hello_time" {
  description = "returns a number"
  value       = fortios_switchcontroller_stpsettings.this.hello_time
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_stpsettings.this.id
}

output "max_age" {
  description = "returns a number"
  value       = fortios_switchcontroller_stpsettings.this.max_age
}

output "max_hops" {
  description = "returns a number"
  value       = fortios_switchcontroller_stpsettings.this.max_hops
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_stpsettings.this.name
}

output "pending_timer" {
  description = "returns a number"
  value       = fortios_switchcontroller_stpsettings.this.pending_timer
}

output "revision" {
  description = "returns a number"
  value       = fortios_switchcontroller_stpsettings.this.revision
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_stpsettings.this.status
}

output "this" {
  value = fortios_switchcontroller_stpsettings.this
}
```

[top](#index)