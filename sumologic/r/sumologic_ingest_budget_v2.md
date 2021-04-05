# sumologic_ingest_budget_v2

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
module "sumologic_ingest_budget_v2" {
  source = "./modules/sumologic/r/sumologic_ingest_budget_v2"

  # action - (required) is a type of string
  action = null
  # audit_threshold - (optional) is a type of number
  audit_threshold = null
  # capacity_bytes - (required) is a type of number
  capacity_bytes = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # reset_time - (required) is a type of string
  reset_time = null
  # scope - (required) is a type of string
  scope = null
  # timezone - (required) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
}

variable "audit_threshold" {
  description = "(optional)"
  type        = number
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "reset_time" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "timezone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_ingest_budget_v2" "this" {
  action          = var.action
  audit_threshold = var.audit_threshold
  capacity_bytes  = var.capacity_bytes
  description     = var.description
  name            = var.name
  reset_time      = var.reset_time
  scope           = var.scope
  timezone        = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_ingest_budget_v2.this.id
}

output "this" {
  value = sumologic_ingest_budget_v2.this
}
```

[top](#index)