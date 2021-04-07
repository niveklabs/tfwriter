# checkpoint_management_https_section

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_https_section" {
  source = "./modules/checkpoint/r/checkpoint_management_https_section"

  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # layer - (required) is a type of string
  layer = null
  # name - (required) is a type of string
  name = null
  # position - (required) is a type of map of string
  position = {}
}
```

[top](#index)

### Variables

```terraform
variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "layer" {
  description = "(required) - Layer that holds the Object. Identified by the Name or UID."
  type        = string
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "position" {
  description = "(required) - Position in the rulebase."
  type        = map(string)
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_https_section" "this" {
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # layer - (required) is a type of string
  layer = var.layer
  # name - (required) is a type of string
  name = var.name
  # position - (required) is a type of map of string
  position = var.position
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_https_section.this.id
}

output "this" {
  value = checkpoint_management_https_section.this
}
```

[top](#index)