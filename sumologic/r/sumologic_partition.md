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
    sumologic = ">= 2.6.2"
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
  # data_forwarding_id - (optional) is a type of string
  data_forwarding_id = null
  # is_compliant - (required) is a type of bool
  is_compliant = null
  # name - (required) is a type of string
  name = null
  # retention_period - (optional) is a type of number
  retention_period = null
  # routing_expression - (required) is a type of string
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

variable "data_forwarding_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_compliant" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "routing_expression" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_partition" "this" {
  analytics_tier     = var.analytics_tier
  data_forwarding_id = var.data_forwarding_id
  is_compliant       = var.is_compliant
  name               = var.name
  retention_period   = var.retention_period
  routing_expression = var.routing_expression
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_partition.this.id
}

output "is_active" {
  description = "returns a bool"
  value       = sumologic_partition.this.is_active
}

output "this" {
  value = sumologic_partition.this
}
```

[top](#index)