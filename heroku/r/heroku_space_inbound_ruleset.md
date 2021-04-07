# heroku_space_inbound_ruleset

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 4.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_space_inbound_ruleset" {
  source = "./modules/heroku/r/heroku_space_inbound_ruleset"

  # space - (required) is a type of string
  space = null

  rule = [{
    action = null
    source = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "space" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      action = string
      source = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "heroku_space_inbound_ruleset" "this" {
  # space - (required) is a type of string
  space = var.space

  dynamic "rule" {
    for_each = var.rule
    content {
      # action - (required) is a type of string
      action = rule.value["action"]
      # source - (required) is a type of string
      source = rule.value["source"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_space_inbound_ruleset.this.id
}

output "this" {
  value = heroku_space_inbound_ruleset.this
}
```

[top](#index)