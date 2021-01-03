# time_rotating

[back](../time.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    time = ">= 0.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "time_rotating" {
  source = "./modules/time/r/time_rotating"

  # rfc3339 - (optional) is a type of string
  rfc3339 = null
  # rotation_days - (optional) is a type of number
  rotation_days = null
  # rotation_hours - (optional) is a type of number
  rotation_hours = null
  # rotation_minutes - (optional) is a type of number
  rotation_minutes = null
  # rotation_months - (optional) is a type of number
  rotation_months = null
  # rotation_rfc3339 - (optional) is a type of string
  rotation_rfc3339 = null
  # rotation_years - (optional) is a type of number
  rotation_years = null
  # triggers - (optional) is a type of map of string
  triggers = {}
}
```

[top](#index)

### Variables

```terraform
variable "rfc3339" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rotation_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rotation_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rotation_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rotation_months" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rotation_rfc3339" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rotation_years" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "triggers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "time_rotating" "this" {
  rfc3339          = var.rfc3339
  rotation_days    = var.rotation_days
  rotation_hours   = var.rotation_hours
  rotation_minutes = var.rotation_minutes
  rotation_months  = var.rotation_months
  rotation_rfc3339 = var.rotation_rfc3339
  rotation_years   = var.rotation_years
  triggers         = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "day" {
  description = "returns a number"
  value       = time_rotating.this.day
}

output "hour" {
  description = "returns a number"
  value       = time_rotating.this.hour
}

output "id" {
  description = "returns a string"
  value       = time_rotating.this.id
}

output "minute" {
  description = "returns a number"
  value       = time_rotating.this.minute
}

output "month" {
  description = "returns a number"
  value       = time_rotating.this.month
}

output "rfc3339" {
  description = "returns a string"
  value       = time_rotating.this.rfc3339
}

output "rotation_rfc3339" {
  description = "returns a string"
  value       = time_rotating.this.rotation_rfc3339
}

output "second" {
  description = "returns a number"
  value       = time_rotating.this.second
}

output "unix" {
  description = "returns a number"
  value       = time_rotating.this.unix
}

output "year" {
  description = "returns a number"
  value       = time_rotating.this.year
}

output "this" {
  value = time_rotating.this
}
```

[top](#index)