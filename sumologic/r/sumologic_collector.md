# sumologic_collector

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
module "sumologic_collector" {
  source = "./modules/sumologic/r/sumologic_collector"

  # category - (optional) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # fields - (optional) is a type of map of string
  fields = {}
  # name - (required) is a type of string
  name = null
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fields" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "sumologic_collector" "this" {
  category    = var.category
  description = var.description
  fields      = var.fields
  name        = var.name
  timezone    = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_collector.this.id
}

output "this" {
  value = sumologic_collector.this
}
```

[top](#index)