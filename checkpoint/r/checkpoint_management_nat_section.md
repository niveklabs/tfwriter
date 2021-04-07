# checkpoint_management_nat_section

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
module "checkpoint_management_nat_section" {
  source = "./modules/checkpoint/r/checkpoint_management_nat_section"

  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (optional) is a type of string
  name = null
  # package - (required) is a type of string
  package = null
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

variable "name" {
  description = "(optional) - Object name."
  type        = string
  default     = null
}

variable "package" {
  description = "(required) - Name of the package."
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
resource "checkpoint_management_nat_section" "this" {
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (optional) is a type of string
  name = var.name
  # package - (required) is a type of string
  package = var.package
  # position - (required) is a type of map of string
  position = var.position
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_nat_section.this.id
}

output "this" {
  value = checkpoint_management_nat_section.this
}
```

[top](#index)