# ciscoasa_access_in_rules

[back](../ciscoasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ciscoasa = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ciscoasa_access_in_rules" {
  source = "./modules/ciscoasa/r/ciscoasa_access_in_rules"

  # interface - (required) is a type of string
  interface = null
  # managed - (optional) is a type of bool
  managed = null

  rule = [{
    active              = null
    destination         = null
    destination_service = null
    id                  = null
    permit              = null
    source              = null
    source_service      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}

variable "managed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      active              = bool
      destination         = string
      destination_service = string
      id                  = string
      permit              = bool
      source              = string
      source_service      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "ciscoasa_access_in_rules" "this" {
  interface = var.interface
  managed   = var.managed

  dynamic "rule" {
    for_each = var.rule
    content {
      active              = rule.value["active"]
      destination         = rule.value["destination"]
      destination_service = rule.value["destination_service"]
      permit              = rule.value["permit"]
      source              = rule.value["source"]
      source_service      = rule.value["source_service"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ciscoasa_access_in_rules.this.id
}

output "this" {
  value = ciscoasa_access_in_rules.this
}
```

[top](#index)