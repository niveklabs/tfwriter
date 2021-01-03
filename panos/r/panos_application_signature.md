# panos_application_signature

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_application_signature" {
  source = "./modules/panos/r/panos_application_signature"

  # application_object - (required) is a type of string
  application_object = null
  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null
  # ordered_match - (optional) is a type of bool
  ordered_match = null
  # scope - (optional) is a type of string
  scope = null
  # vsys - (optional) is a type of string
  vsys = null

  and_condition = [{
    name = null
    or_condition = [{
      equal_to = [{
        context  = null
        mask     = null
        position = null
        value    = null
      }]
      greater_than = [{
        context    = null
        qualifiers = {}
        value      = null
      }]
      less_than = [{
        context    = null
        qualifiers = {}
        value      = null
      }]
      name = null
      pattern_match = [{
        context    = null
        pattern    = null
        qualifiers = {}
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_object" {
  description = "(required)"
  type        = string
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ordered_match" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "and_condition" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      or_condition = list(object(
        {
          equal_to = list(object(
            {
              context  = string
              mask     = string
              position = string
              value    = string
            }
          ))
          greater_than = list(object(
            {
              context    = string
              qualifiers = map(string)
              value      = string
            }
          ))
          less_than = list(object(
            {
              context    = string
              qualifiers = map(string)
              value      = string
            }
          ))
          name = string
          pattern_match = list(object(
            {
              context    = string
              pattern    = string
              qualifiers = map(string)
            }
          ))
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_application_signature" "this" {
  application_object = var.application_object
  comment            = var.comment
  name               = var.name
  ordered_match      = var.ordered_match
  scope              = var.scope
  vsys               = var.vsys

  dynamic "and_condition" {
    for_each = var.and_condition
    content {

      dynamic "or_condition" {
        for_each = and_condition.value.or_condition
        content {

          dynamic "equal_to" {
            for_each = or_condition.value.equal_to
            content {
              context  = equal_to.value["context"]
              mask     = equal_to.value["mask"]
              position = equal_to.value["position"]
              value    = equal_to.value["value"]
            }
          }

          dynamic "greater_than" {
            for_each = or_condition.value.greater_than
            content {
              context    = greater_than.value["context"]
              qualifiers = greater_than.value["qualifiers"]
              value      = greater_than.value["value"]
            }
          }

          dynamic "less_than" {
            for_each = or_condition.value.less_than
            content {
              context    = less_than.value["context"]
              qualifiers = less_than.value["qualifiers"]
              value      = less_than.value["value"]
            }
          }

          dynamic "pattern_match" {
            for_each = or_condition.value.pattern_match
            content {
              context    = pattern_match.value["context"]
              pattern    = pattern_match.value["pattern"]
              qualifiers = pattern_match.value["qualifiers"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_application_signature.this.id
}

output "this" {
  value = panos_application_signature.this
}
```

[top](#index)