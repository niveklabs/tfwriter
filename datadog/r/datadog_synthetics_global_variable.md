# datadog_synthetics_global_variable

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_synthetics_global_variable" {
  source = "./modules/datadog/r/datadog_synthetics_global_variable"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # secure - (optional) is a type of bool
  secure = null
  # tags - (optional) is a type of list of string
  tags = []
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "secure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_synthetics_global_variable" "this" {
  description = var.description
  name        = var.name
  secure      = var.secure
  tags        = var.tags
  value       = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_synthetics_global_variable.this.id
}

output "this" {
  value = datadog_synthetics_global_variable.this
}
```

[top](#index)