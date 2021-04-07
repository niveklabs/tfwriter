# random_integer

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
    random = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "random_integer" {
  source = "./modules/random/r/random_integer"

  # keepers - (optional) is a type of map of string
  keepers = {}
  # max - (required) is a type of number
  max = null
  # min - (required) is a type of number
  min = null
  # seed - (optional) is a type of string
  seed = null
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

variable "max" {
  description = "(required) - The maximum inclusive value of the range."
  type        = number
}

variable "min" {
  description = "(required) - The minimum inclusive value of the range."
  type        = number
}

variable "seed" {
  description = "(optional) - A custom seed to always produce the same value."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "random_integer" "this" {
  # keepers - (optional) is a type of map of string
  keepers = var.keepers
  # max - (required) is a type of number
  max = var.max
  # min - (required) is a type of number
  min = var.min
  # seed - (optional) is a type of string
  seed = var.seed
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = random_integer.this.id
}

output "result" {
  description = "returns a number"
  value       = random_integer.this.result
}

output "this" {
  value = random_integer.this
}
```

[top](#index)