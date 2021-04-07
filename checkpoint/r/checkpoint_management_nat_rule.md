# checkpoint_management_nat_rule

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
module "checkpoint_management_nat_rule" {
  source = "./modules/checkpoint/r/checkpoint_management_nat_rule"

  # comments - (optional) is a type of string
  comments = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # install_on - (optional) is a type of set of string
  install_on = []
  # method - (optional) is a type of string
  method = null
  # name - (optional) is a type of string
  name = null
  # original_destination - (optional) is a type of string
  original_destination = null
  # original_service - (optional) is a type of string
  original_service = null
  # original_source - (optional) is a type of string
  original_source = null
  # package - (required) is a type of string
  package = null
  # position - (required) is a type of map of string
  position = {}
  # translated_destination - (optional) is a type of string
  translated_destination = null
  # translated_service - (optional) is a type of string
  translated_service = null
  # translated_source - (optional) is a type of string
  translated_source = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Enable/Disable the rule."
  type        = bool
  default     = null
}

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

variable "install_on" {
  description = "(optional) - Which Gateways identified by the name or UID to install the policy on."
  type        = set(string)
  default     = null
}

variable "method" {
  description = "(optional) - Nat method."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Rule name."
  type        = string
  default     = null
}

variable "original_destination" {
  description = "(optional) - Original destination."
  type        = string
  default     = null
}

variable "original_service" {
  description = "(optional) - Original service."
  type        = string
  default     = null
}

variable "original_source" {
  description = "(optional) - Original source."
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

variable "translated_destination" {
  description = "(optional) - Translated destination."
  type        = string
  default     = null
}

variable "translated_service" {
  description = "(optional) - Translated service."
  type        = string
  default     = null
}

variable "translated_source" {
  description = "(optional) - Translated source."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_nat_rule" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # install_on - (optional) is a type of set of string
  install_on = var.install_on
  # method - (optional) is a type of string
  method = var.method
  # name - (optional) is a type of string
  name = var.name
  # original_destination - (optional) is a type of string
  original_destination = var.original_destination
  # original_service - (optional) is a type of string
  original_service = var.original_service
  # original_source - (optional) is a type of string
  original_source = var.original_source
  # package - (required) is a type of string
  package = var.package
  # position - (required) is a type of map of string
  position = var.position
  # translated_destination - (optional) is a type of string
  translated_destination = var.translated_destination
  # translated_service - (optional) is a type of string
  translated_service = var.translated_service
  # translated_source - (optional) is a type of string
  translated_source = var.translated_source
}
```

[top](#index)

### Outputs

```terraform
output "auto_generated" {
  description = "returns a bool"
  value       = checkpoint_management_nat_rule.this.auto_generated
}

output "id" {
  description = "returns a string"
  value       = checkpoint_management_nat_rule.this.id
}

output "this" {
  value = checkpoint_management_nat_rule.this
}
```

[top](#index)