# okta_factor

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_factor" {
  source = "./modules/okta/r/okta_factor"

  # active - (optional) is a type of bool
  active = null
  # provider_id - (required) is a type of string
  provider_id = null
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional) - Is this provider active?"
  type        = bool
  default     = null
}

variable "provider_id" {
  description = "(required) - Factor provider ID"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_factor" "this" {
  active      = var.active
  provider_id = var.provider_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_factor.this.id
}

output "this" {
  value = okta_factor.this
}
```

[top](#index)