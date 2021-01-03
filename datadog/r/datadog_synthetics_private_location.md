# datadog_synthetics_private_location

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
module "datadog_synthetics_private_location" {
  source = "./modules/datadog/r/datadog_synthetics_private_location"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
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

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_synthetics_private_location" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "config" {
  description = "returns a string"
  value       = datadog_synthetics_private_location.this.config
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = datadog_synthetics_private_location.this.id
}

output "this" {
  value = datadog_synthetics_private_location.this
}
```

[top](#index)