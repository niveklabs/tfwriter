# time_offset

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
module "time_offset" {
  source = "./modules/time/r/time_offset"

  # base_rfc3339 - (optional) is a type of string
  base_rfc3339 = null
  # offset_days - (optional) is a type of number
  offset_days = null
  # offset_hours - (optional) is a type of number
  offset_hours = null
  # offset_minutes - (optional) is a type of number
  offset_minutes = null
  # offset_months - (optional) is a type of number
  offset_months = null
  # offset_seconds - (optional) is a type of number
  offset_seconds = null
  # offset_years - (optional) is a type of number
  offset_years = null
  # triggers - (optional) is a type of map of string
  triggers = {}
}
```

[top](#index)

### Variables

```terraform
variable "base_rfc3339" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "offset_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "offset_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "offset_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "offset_months" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "offset_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "offset_years" {
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
resource "time_offset" "this" {
  base_rfc3339   = var.base_rfc3339
  offset_days    = var.offset_days
  offset_hours   = var.offset_hours
  offset_minutes = var.offset_minutes
  offset_months  = var.offset_months
  offset_seconds = var.offset_seconds
  offset_years   = var.offset_years
  triggers       = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "base_rfc3339" {
  description = "returns a string"
  value       = time_offset.this.base_rfc3339
}

output "day" {
  description = "returns a number"
  value       = time_offset.this.day
}

output "hour" {
  description = "returns a number"
  value       = time_offset.this.hour
}

output "id" {
  description = "returns a string"
  value       = time_offset.this.id
}

output "minute" {
  description = "returns a number"
  value       = time_offset.this.minute
}

output "month" {
  description = "returns a number"
  value       = time_offset.this.month
}

output "rfc3339" {
  description = "returns a string"
  value       = time_offset.this.rfc3339
}

output "second" {
  description = "returns a number"
  value       = time_offset.this.second
}

output "unix" {
  description = "returns a number"
  value       = time_offset.this.unix
}

output "year" {
  description = "returns a number"
  value       = time_offset.this.year
}

output "this" {
  value = time_offset.this
}
```

[top](#index)