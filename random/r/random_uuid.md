# random_uuid

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
module "random_uuid" {
  source = "./modules/random/r/random_uuid"

  # keepers - (optional) is a type of map of string
  keepers = {}
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
```

[top](#index)

### Resource

```terraform
resource "random_uuid" "this" {
  # keepers - (optional) is a type of map of string
  keepers = var.keepers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = random_uuid.this.id
}

output "result" {
  description = "returns a string"
  value       = random_uuid.this.result
}

output "this" {
  value = random_uuid.this
}
```

[top](#index)