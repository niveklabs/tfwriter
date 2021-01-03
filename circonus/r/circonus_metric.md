# circonus_metric

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.11.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_metric" {
  source = "./modules/circonus/r/circonus_metric"

  # active - (optional) is a type of bool
  active = null
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional) - Enables or disables the metric"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the metric"
  type        = string
}

variable "type" {
  description = "(required) - Type of metric (e.g. numeric, histogram, text)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "circonus_metric" "this" {
  active = var.active
  name   = var.name
  type   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = circonus_metric.this.id
}

output "this" {
  value = circonus_metric.this
}
```

[top](#index)