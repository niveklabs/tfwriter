# random_password

[back](../random.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    random = ">= 3.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "random_password" {
  source = "./modules/random/r/random_password"

  # keepers - (optional) is a type of map of string
  keepers = {}
  # length - (required) is a type of number
  length = null
  # lower - (optional) is a type of bool
  lower = null
  # min_lower - (optional) is a type of number
  min_lower = null
  # min_numeric - (optional) is a type of number
  min_numeric = null
  # min_special - (optional) is a type of number
  min_special = null
  # min_upper - (optional) is a type of number
  min_upper = null
  # number - (optional) is a type of bool
  number = null
  # override_special - (optional) is a type of string
  override_special = null
  # special - (optional) is a type of bool
  special = null
  # upper - (optional) is a type of bool
  upper = null
}
```

[top](#index)

### Variables

```terraform
variable "keepers" {
  description = "(optional) - Arbitrary map of values that, when changed, will trigger recreation of resource. See [the main provider documentation](../index.html) for more information."
  type        = map(string)
  default     = null
}

variable "length" {
  description = "(required) - The length of the string desired."
  type        = number
}

variable "lower" {
  description = "(optional) - Include lowercase alphabet characters in the result."
  type        = bool
  default     = null
}

variable "min_lower" {
  description = "(optional) - Minimum number of lowercase alphabet characters in the result."
  type        = number
  default     = null
}

variable "min_numeric" {
  description = "(optional) - Minimum number of numeric characters in the result."
  type        = number
  default     = null
}

variable "min_special" {
  description = "(optional) - Minimum number of special characters in the result."
  type        = number
  default     = null
}

variable "min_upper" {
  description = "(optional) - Minimum number of uppercase alphabet characters in the result."
  type        = number
  default     = null
}

variable "number" {
  description = "(optional) - Include numeric characters in the result."
  type        = bool
  default     = null
}

variable "override_special" {
  description = "(optional) - Supply your own list of special characters to use for string generation.  This overrides the default character list in the special argument.  The `special` argument must still be set to true for any overwritten characters to be used in generation."
  type        = string
  default     = null
}

variable "special" {
  description = "(optional) - Include special characters in the result. These are `!@#$%&*()-_=+[]{}<>:?`"
  type        = bool
  default     = null
}

variable "upper" {
  description = "(optional) - Include uppercase alphabet characters in the result."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "random_password" "this" {
  keepers          = var.keepers
  length           = var.length
  lower            = var.lower
  min_lower        = var.min_lower
  min_numeric      = var.min_numeric
  min_special      = var.min_special
  min_upper        = var.min_upper
  number           = var.number
  override_special = var.override_special
  special          = var.special
  upper            = var.upper
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = random_password.this.id
}

output "result" {
  description = "returns a string"
  value       = random_password.this.result
  sensitive   = true
}

output "this" {
  value = random_password.this
}
```

[top](#index)