# fortios_router_communitylist

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_router_communitylist" {
  source = "./modules/fortios/r/fortios_router_communitylist"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null

  rule = [{
    action = null
    id     = null
    match  = null
    regexp = null
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

variable "type" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      id     = number
      match  = string
      regexp = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_communitylist" "this" {
  name = var.name
  type = var.type

  dynamic "rule" {
    for_each = var.rule
    content {
      action = rule.value["action"]
      id     = rule.value["id"]
      match  = rule.value["match"]
      regexp = rule.value["regexp"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_communitylist.this.id
}

output "this" {
  value = fortios_router_communitylist.this
}
```

[top](#index)