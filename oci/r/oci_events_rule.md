# oci_events_rule

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_events_rule" {
  source = "./modules/oci/r/oci_events_rule"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # condition - (required) is a type of string
  condition = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_enabled - (required) is a type of bool
  is_enabled = null

  actions = [{
    actions = [{
      action_type       = null
      description       = null
      function_id       = null
      id                = null
      is_enabled        = null
      lifecycle_message = null
      state             = null
      stream_id         = null
      topic_id          = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_enabled" {
  description = "(required)"
  type        = bool
}

variable "actions" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      actions = set(object(
        {
          action_type       = string
          description       = string
          function_id       = string
          id                = string
          is_enabled        = bool
          lifecycle_message = string
          state             = string
          stream_id         = string
          topic_id          = string
        }
      ))
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_events_rule" "this" {
  compartment_id = var.compartment_id
  condition      = var.condition
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  is_enabled     = var.is_enabled

  dynamic "actions" {
    for_each = var.actions
    content {

      dynamic "actions" {
        for_each = actions.value.actions
        content {
          action_type = actions.value["action_type"]
          description = actions.value["description"]
          function_id = actions.value["function_id"]
          is_enabled  = actions.value["is_enabled"]
          stream_id   = actions.value["stream_id"]
          topic_id    = actions.value["topic_id"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_events_rule.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_events_rule.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_events_rule.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_events_rule.this.id
}

output "lifecycle_message" {
  description = "returns a string"
  value       = oci_events_rule.this.lifecycle_message
}

output "state" {
  description = "returns a string"
  value       = oci_events_rule.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_events_rule.this.time_created
}

output "this" {
  value = oci_events_rule.this
}
```

[top](#index)