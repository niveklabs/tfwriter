# pagerduty_ruleset

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "pagerduty_ruleset" {
  source = "./modules/pagerduty/d/pagerduty_ruleset"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_ruleset" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.pagerduty_ruleset.this.id
}

output "routing_keys" {
  description = "returns a list of string"
  value       = data.pagerduty_ruleset.this.routing_keys
}

output "this" {
  value = pagerduty_ruleset.this
}
```

[top](#index)