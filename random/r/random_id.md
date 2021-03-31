# random_id

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
module "random_id" {
  source = "./modules/random/r/random_id"

  # byte_length - (required) is a type of number
  byte_length = null
  # keepers - (optional) is a type of map of string
  keepers = {}
  # prefix - (optional) is a type of string
  prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "byte_length" {
  description = "(required) - The number of random bytes to produce. The minimum value is 1, which produces eight bits of randomness."
  type        = number
}

variable "keepers" {
  description = "(optional) - Arbitrary map of values that, when changed, will trigger recreation of resource. See [the main provider documentation](../index.html) for more information."
  type        = map(string)
  default     = null
}

variable "prefix" {
  description = "(optional) - Arbitrary string to prefix the output value with. This string is supplied as-is, meaning it is not guaranteed to be URL-safe or base64 encoded."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "random_id" "this" {
  byte_length = var.byte_length
  keepers     = var.keepers
  prefix      = var.prefix
}
```

[top](#index)

### Outputs

```terraform
output "b64_std" {
  description = "returns a string"
  value       = random_id.this.b64_std
}

output "b64_url" {
  description = "returns a string"
  value       = random_id.this.b64_url
}

output "dec" {
  description = "returns a string"
  value       = random_id.this.dec
}

output "hex" {
  description = "returns a string"
  value       = random_id.this.hex
}

output "id" {
  description = "returns a string"
  value       = random_id.this.id
}

output "this" {
  value = random_id.this
}
```

[top](#index)