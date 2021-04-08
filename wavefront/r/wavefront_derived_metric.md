# wavefront_derived_metric

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_derived_metric" {
  source = "./modules/wavefront/r/wavefront_derived_metric"

  # additional_information - (optional) is a type of string
  additional_information = null
  # minutes - (required) is a type of number
  minutes = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "additional_information" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "minutes" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_derived_metric" "this" {
  # additional_information - (optional) is a type of string
  additional_information = var.additional_information
  # minutes - (required) is a type of number
  minutes = var.minutes
  # name - (required) is a type of string
  name = var.name
  # query - (required) is a type of string
  query = var.query
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_derived_metric.this.id
}

output "this" {
  value = wavefront_derived_metric.this
}
```

[top](#index)