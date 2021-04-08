# auth0_rule_config

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_rule_config" {
  source = "./modules/auth0/r/auth0_rule_config"

  # key - (required) is a type of string
  key = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "auth0_rule_config" "this" {
  # key - (required) is a type of string
  key = var.key
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_rule_config.this.id
}

output "this" {
  value = auth0_rule_config.this
}
```

[top](#index)