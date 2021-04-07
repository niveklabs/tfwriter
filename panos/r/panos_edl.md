# panos_edl

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_edl" {
  source = null

  # certificate_profile - (optional) is a type of string
  certificate_profile = null
  # description - (optional) is a type of string
  description = null
  # exceptions - (optional) is a type of list of string
  exceptions = []
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # repeat - (optional) is a type of string
  repeat = null
  # repeat_at - (optional) is a type of string
  repeat_at = null
  # repeat_day_of_month - (optional) is a type of number
  repeat_day_of_month = null
  # repeat_day_of_week - (optional) is a type of string
  repeat_day_of_week = null
  # source - (optional) is a type of string
  # type - (optional) is a type of string
  type = null
  # username - (optional) is a type of string
  username = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exceptions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repeat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repeat_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repeat_day_of_month" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "repeat_day_of_week" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_edl" "this" {
  # certificate_profile - (optional) is a type of string
  certificate_profile = var.certificate_profile
  # description - (optional) is a type of string
  description = var.description
  # exceptions - (optional) is a type of list of string
  exceptions = var.exceptions
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # repeat - (optional) is a type of string
  repeat = var.repeat
  # repeat_at - (optional) is a type of string
  repeat_at = var.repeat_at
  # repeat_day_of_month - (optional) is a type of number
  repeat_day_of_month = var.repeat_day_of_month
  # repeat_day_of_week - (optional) is a type of string
  repeat_day_of_week = var.repeat_day_of_week
  # source - (optional) is a type of string
  source = var.source
  # type - (optional) is a type of string
  type = var.type
  # username - (optional) is a type of string
  username = var.username
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_edl.this.id
}

output "password_enc" {
  description = "returns a string"
  value       = panos_edl.this.password_enc
  sensitive   = true
}

output "this" {
  value = panos_edl.this
}
```

[top](#index)