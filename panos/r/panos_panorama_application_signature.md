# panos_panorama_application_signature

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
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_application_signature" {
  source = "./modules/panos/r/panos_panorama_application_signature"

  # application_object - (required) is a type of string
  application_object = null
  # comment - (optional) is a type of string
  comment = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # ordered_match - (optional) is a type of bool
  ordered_match = null
  # scope - (optional) is a type of string
  scope = null

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

variable "device_group" {
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
resource "panos_panorama_application_signature" "this" {
  # application_object - (required) is a type of string
  application_object = var.application_object
  # comment - (optional) is a type of string
  comment = var.comment
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # ordered_match - (optional) is a type of bool
  ordered_match = var.ordered_match
  # scope - (optional) is a type of string
  scope = var.scope

  dynamic "and_condition" {
    for_each = var.and_condition
    content {

      dynamic "or_condition" {
        for_each = and_condition.value.or_condition
        content {

          dynamic "equal_to" {
            for_each = or_condition.value.equal_to
            content {
              # context - (required) is a type of string
              context = equal_to.value["context"]
              # mask - (optional) is a type of string
              mask = equal_to.value["mask"]
              # position - (optional) is a type of string
              position = equal_to.value["position"]
              # value - (required) is a type of string
              value = equal_to.value["value"]
            }
          }

          dynamic "greater_than" {
            for_each = or_condition.value.greater_than
            content {
              # context - (required) is a type of string
              context = greater_than.value["context"]
              # qualifiers - (optional) is a type of map of string
              qualifiers = greater_than.value["qualifiers"]
              # value - (required) is a type of string
              value = greater_than.value["value"]
            }
          }

          dynamic "less_than" {
            for_each = or_condition.value.less_than
            content {
              # context - (required) is a type of string
              context = less_than.value["context"]
              # qualifiers - (optional) is a type of map of string
              qualifiers = less_than.value["qualifiers"]
              # value - (required) is a type of string
              value = less_than.value["value"]
            }
          }

          dynamic "pattern_match" {
            for_each = or_condition.value.pattern_match
            content {
              # context - (required) is a type of string
              context = pattern_match.value["context"]
              # pattern - (required) is a type of string
              pattern = pattern_match.value["pattern"]
              # qualifiers - (optional) is a type of map of string
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
  value       = panos_panorama_application_signature.this.id
}

output "this" {
  value = panos_panorama_application_signature.this
}
```

[top](#index)