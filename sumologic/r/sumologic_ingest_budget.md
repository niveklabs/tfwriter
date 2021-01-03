# sumologic_ingest_budget

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
module "sumologic_ingest_budget" {
  source = "./modules/sumologic/r/sumologic_ingest_budget"

  # action - (optional) is a type of string
  action = null
  # capacity_bytes - (required) is a type of number
  capacity_bytes = null
  # description - (optional) is a type of string
  description = null
  # field_value - (required) is a type of string
  field_value = null
  # name - (required) is a type of string
  name = null
  # reset_time - (optional) is a type of string
  reset_time = null
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capacity_bytes" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "field_value" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "reset_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_ingest_budget" "this" {
  action         = var.action
  capacity_bytes = var.capacity_bytes
  description    = var.description
  field_value    = var.field_value
  name           = var.name
  reset_time     = var.reset_time
  timezone       = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_ingest_budget.this.id
}

output "this" {
  value = sumologic_ingest_budget.this
}
```

[top](#index)