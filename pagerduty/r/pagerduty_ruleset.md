# pagerduty_ruleset

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
module "pagerduty_ruleset" {
  source = "./modules/pagerduty/r/pagerduty_ruleset"

  # name - (required) is a type of string
  name = null

  team = [{
    id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "team" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_ruleset" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "team" {
    for_each = var.team
    content {
      # id - (required) is a type of string
      id = team.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_ruleset.this.id
}

output "routing_keys" {
  description = "returns a list of string"
  value       = pagerduty_ruleset.this.routing_keys
}

output "type" {
  description = "returns a string"
  value       = pagerduty_ruleset.this.type
}

output "this" {
  value = pagerduty_ruleset.this
}
```

[top](#index)