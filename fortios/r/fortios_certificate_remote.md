# fortios_certificate_remote

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
module "fortios_certificate_remote" {
  source = null

  # name - (optional) is a type of string
  name = null
  # range - (optional) is a type of string
  range = null
  # remote - (optional) is a type of string
  remote = null
  # source - (optional) is a type of string
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

variable "range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_certificate_remote" "this" {
  name   = var.name
  range  = var.range
  remote = var.remote
  source = var.source
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_certificate_remote.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_certificate_remote.this.name
}

output "range" {
  description = "returns a string"
  value       = fortios_certificate_remote.this.range
}

output "remote" {
  description = "returns a string"
  value       = fortios_certificate_remote.this.remote
}

output "source" {
  description = "returns a string"
  value       = fortios_certificate_remote.this.source
}

output "this" {
  value = fortios_certificate_remote.this
}
```

[top](#index)