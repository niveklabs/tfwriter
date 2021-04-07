# pagerduty_addon

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_addon" {
  source = "./modules/pagerduty/r/pagerduty_addon"

  # name - (required) is a type of string
  name = null
  # src - (required) is a type of string
  src = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "src" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_addon" "this" {
  # name - (required) is a type of string
  name = var.name
  # src - (required) is a type of string
  src = var.src
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_addon.this.id
}

output "this" {
  value = pagerduty_addon.this
}
```

[top](#index)