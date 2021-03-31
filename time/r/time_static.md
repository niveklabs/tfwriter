# time_static

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
    time = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "time_static" {
  source = "./modules/time/r/time_static"

  # rfc3339 - (optional) is a type of string
  rfc3339 = null
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

variable "triggers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "time_static" "this" {
  rfc3339  = var.rfc3339
  triggers = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "day" {
  description = "returns a number"
  value       = time_static.this.day
}

output "hour" {
  description = "returns a number"
  value       = time_static.this.hour
}

output "id" {
  description = "returns a string"
  value       = time_static.this.id
}

output "minute" {
  description = "returns a number"
  value       = time_static.this.minute
}

output "month" {
  description = "returns a number"
  value       = time_static.this.month
}

output "rfc3339" {
  description = "returns a string"
  value       = time_static.this.rfc3339
}

output "second" {
  description = "returns a number"
  value       = time_static.this.second
}

output "unix" {
  description = "returns a number"
  value       = time_static.this.unix
}

output "year" {
  description = "returns a number"
  value       = time_static.this.year
}

output "this" {
  value = time_static.this
}
```

[top](#index)