# random_pet

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
module "random_pet" {
  source = "./modules/random/r/random_pet"

  # keepers - (optional) is a type of map of string
  keepers = {}
  # length - (optional) is a type of number
  length = null
  # prefix - (optional) is a type of string
  prefix = null
  # separator - (optional) is a type of string
  separator = null
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
  description = "(optional) - The length (in words) of the pet name."
  type        = number
  default     = null
}

variable "prefix" {
  description = "(optional) - A string to prefix the name with."
  type        = string
  default     = null
}

variable "separator" {
  description = "(optional) - The character to separate words in the pet name."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "random_pet" "this" {
  # keepers - (optional) is a type of map of string
  keepers = var.keepers
  # length - (optional) is a type of number
  length = var.length
  # prefix - (optional) is a type of string
  prefix = var.prefix
  # separator - (optional) is a type of string
  separator = var.separator
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = random_pet.this.id
}

output "this" {
  value = random_pet.this
}
```

[top](#index)