# nutanix_access_control_policy

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_access_control_policy" {
  source = "./modules/nutanix/r/nutanix_access_control_policy"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null

  categories = [{
    name  = null
    value = null
  }]

  context_filter_list = [{
    entity_filter_expression_list = [{
      left_hand_side_entity_type = null
      operator                   = null
      right_hand_side = [{
        categories = [{
          name  = null
          value = []
        }]
        collection = null
        uuid_list  = []
      }]
    }]
    scope_filter_expression_list = [{
      left_hand_side = null
      operator       = null
      right_hand_side = [{
        categories = [{
          name  = null
          value = []
        }]
        collection = null
        uuid_list  = []
      }]
    }]
  }]

  owner_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  role_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  user_group_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  user_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "context_filter_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      entity_filter_expression_list = list(object(
        {
          left_hand_side_entity_type = string
          operator                   = string
          right_hand_side = list(object(
            {
              categories = list(object(
                {
                  name  = string
                  value = set(string)
                }
              ))
              collection = string
              uuid_list  = set(string)
            }
          ))
        }
      ))
      scope_filter_expression_list = list(object(
        {
          left_hand_side = string
          operator       = string
          right_hand_side = list(object(
            {
              categories = list(object(
                {
                  name  = string
                  value = set(string)
                }
              ))
              collection = string
              uuid_list  = set(string)
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "owner_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "role_reference" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
}

variable "user_group_reference_list" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "user_reference_list" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_access_control_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

  dynamic "context_filter_list" {
    for_each = var.context_filter_list
    content {

      dynamic "entity_filter_expression_list" {
        for_each = context_filter_list.value.entity_filter_expression_list
        content {
          # left_hand_side_entity_type - (optional) is a type of string
          left_hand_side_entity_type = entity_filter_expression_list.value["left_hand_side_entity_type"]
          # operator - (required) is a type of string
          operator = entity_filter_expression_list.value["operator"]

          dynamic "right_hand_side" {
            for_each = entity_filter_expression_list.value.right_hand_side
            content {
              # collection - (optional) is a type of string
              collection = right_hand_side.value["collection"]
              # uuid_list - (optional) is a type of set of string
              uuid_list = right_hand_side.value["uuid_list"]

              dynamic "categories" {
                for_each = right_hand_side.value.categories
                content {
                  # name - (optional) is a type of string
                  name = categories.value["name"]
                  # value - (optional) is a type of set of string
                  value = categories.value["value"]
                }
              }

            }
          }

        }
      }

      dynamic "scope_filter_expression_list" {
        for_each = context_filter_list.value.scope_filter_expression_list
        content {
          # left_hand_side - (required) is a type of string
          left_hand_side = scope_filter_expression_list.value["left_hand_side"]
          # operator - (required) is a type of string
          operator = scope_filter_expression_list.value["operator"]

          dynamic "right_hand_side" {
            for_each = scope_filter_expression_list.value.right_hand_side
            content {
              # collection - (optional) is a type of string
              collection = right_hand_side.value["collection"]
              # uuid_list - (optional) is a type of set of string
              uuid_list = right_hand_side.value["uuid_list"]

              dynamic "categories" {
                for_each = right_hand_side.value.categories
                content {
                  # name - (optional) is a type of string
                  name = categories.value["name"]
                  # value - (optional) is a type of set of string
                  value = categories.value["value"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "owner_reference" {
    for_each = var.owner_reference
    content {
      # kind - (optional) is a type of string
      kind = owner_reference.value["kind"]
      # name - (optional) is a type of string
      name = owner_reference.value["name"]
      # uuid - (optional) is a type of string
      uuid = owner_reference.value["uuid"]
    }
  }

  dynamic "role_reference" {
    for_each = var.role_reference
    content {
      # kind - (required) is a type of string
      kind = role_reference.value["kind"]
      # name - (optional) is a type of string
      name = role_reference.value["name"]
      # uuid - (required) is a type of string
      uuid = role_reference.value["uuid"]
    }
  }

  dynamic "user_group_reference_list" {
    for_each = var.user_group_reference_list
    content {
      # name - (optional) is a type of string
      name = user_group_reference_list.value["name"]
      # uuid - (required) is a type of string
      uuid = user_group_reference_list.value["uuid"]
    }
  }

  dynamic "user_reference_list" {
    for_each = var.user_reference_list
    content {
      # name - (optional) is a type of string
      name = user_reference_list.value["name"]
      # uuid - (required) is a type of string
      uuid = user_reference_list.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_access_control_policy.this.api_version
}

output "description" {
  description = "returns a string"
  value       = nutanix_access_control_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_access_control_policy.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_access_control_policy.this.metadata
}

output "name" {
  description = "returns a string"
  value       = nutanix_access_control_policy.this.name
}

output "state" {
  description = "returns a string"
  value       = nutanix_access_control_policy.this.state
}

output "this" {
  value = nutanix_access_control_policy.this
}
```

[top](#index)