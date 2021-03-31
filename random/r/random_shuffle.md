# random_shuffle

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
module "random_shuffle" {
  source = "./modules/random/r/random_shuffle"

  # input - (required) is a type of list of string
  input = []
  # keepers - (optional) is a type of map of string
  keepers = {}
  # result_count - (optional) is a type of number
  result_count = null
  # seed - (optional) is a type of string
  seed = null
}
```

[top](#index)

### Variables

```terraform
variable "input" {
  description = "(required) - The list of strings to shuffle."
  type        = list(string)
}

variable "keepers" {
  description = "(optional) - Arbitrary map of values that, when changed, will trigger recreation of resource. See [the main provider documentation](../index.html) for more information."
  type        = map(string)
  default     = null
}

variable "result_count" {
  description = "(optional) - The number of results to return. Defaults to the number of items in the `input` list. If fewer items are requested, some elements will be excluded from the result. If more items are requested, items will be repeated in the result but not more frequently than the number of items in the input list."
  type        = number
  default     = null
}

variable "seed" {
  description = "(optional) - Arbitrary string with which to seed the random number generator, in order to produce less-volatile permutations of the list.\n\n**Important:** Even with an identical seed, it is not guaranteed that the same permutation will be produced across different versions of Terraform. This argument causes the result to be *less volatile*, but not fixed for all time."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "random_shuffle" "this" {
  input        = var.input
  keepers      = var.keepers
  result_count = var.result_count
  seed         = var.seed
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = random_shuffle.this.id
}

output "result" {
  description = "returns a list of string"
  value       = random_shuffle.this.result
}

output "this" {
  value = random_shuffle.this
}
```

[top](#index)