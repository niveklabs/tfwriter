# sumologic_partition

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_partition" {
  source = "./modules/sumologic/r/sumologic_partition"

  # analytics_tier - (optional) is a type of string
  analytics_tier = null
  # is_compliant - (optional) is a type of bool
  is_compliant = null
  # name - (required) is a type of string
  name = null
  # reduce_retention_period_immediately - (optional) is a type of bool
  reduce_retention_period_immediately = null
  # retention_period - (optional) is a type of number
  retention_period = null
  # routing_expression - (optional) is a type of string
  routing_expression = null
}
```

[top](#index)

### Variables

```terraform
variable "analytics_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_compliant" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "reduce_retention_period_immediately" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "routing_expression" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_partition" "this" {
  # analytics_tier - (optional) is a type of string
  analytics_tier = var.analytics_tier
  # is_compliant - (optional) is a type of bool
  is_compliant = var.is_compliant
  # name - (required) is a type of string
  name = var.name
  # reduce_retention_period_immediately - (optional) is a type of bool
  reduce_retention_period_immediately = var.reduce_retention_period_immediately
  # retention_period - (optional) is a type of number
  retention_period = var.retention_period
  # routing_expression - (optional) is a type of string
  routing_expression = var.routing_expression
}
```

[top](#index)

### Outputs

```terraform
output "data_forwarding_id" {
  description = "returns a string"
  value       = sumologic_partition.this.data_forwarding_id
}

output "id" {
  description = "returns a string"
  value       = sumologic_partition.this.id
}

output "index_type" {
  description = "returns a string"
  value       = sumologic_partition.this.index_type
}

output "is_active" {
  description = "returns a bool"
  value       = sumologic_partition.this.is_active
}

output "total_bytes" {
  description = "returns a number"
  value       = sumologic_partition.this.total_bytes
}

output "this" {
  value = sumologic_partition.this
}
```

[top](#index)