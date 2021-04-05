# sumologic_scheduled_view

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
module "sumologic_scheduled_view" {
  source = "./modules/sumologic/r/sumologic_scheduled_view"

  # data_forwarding_id - (optional) is a type of string
  data_forwarding_id = null
  # index_name - (required) is a type of string
  index_name = null
  # parsing_mode - (optional) is a type of string
  parsing_mode = null
  # query - (required) is a type of string
  query = null
  # reduce_retention_period_immediately - (optional) is a type of bool
  reduce_retention_period_immediately = null
  # retention_period - (optional) is a type of number
  retention_period = null
  # start_time - (required) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "data_forwarding_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "index_name" {
  description = "(required)"
  type        = string
}

variable "parsing_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query" {
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

variable "start_time" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_scheduled_view" "this" {
  data_forwarding_id                  = var.data_forwarding_id
  index_name                          = var.index_name
  parsing_mode                        = var.parsing_mode
  query                               = var.query
  reduce_retention_period_immediately = var.reduce_retention_period_immediately
  retention_period                    = var.retention_period
  start_time                          = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_scheduled_view.this.id
}

output "this" {
  value = sumologic_scheduled_view.this
}
```

[top](#index)