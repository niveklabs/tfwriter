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
    datadog = ">= 2.24.0"
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
  description = "(optional) - Description of the private location."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Synthetics private location name."
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tags to associate with your synthetics private location."
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