# alicloud_ga_forwarding_rule

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ga_forwarding_rule" {
  source = "./modules/alicloud/r/alicloud_ga_forwarding_rule"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # forwarding_rule_name - (optional) is a type of string
  forwarding_rule_name = null
  # listener_id - (required) is a type of string
  listener_id = null
  # priority - (optional) is a type of number
  priority = null

  rule_actions = [{
    forward_group_config = [{
      server_group_tuples = [{
        endpoint_group_id = null
      }]
    }]
    order            = null
    rule_action_type = null
  }]

  rule_conditions = [{
    host_config = [{
      values = []
    }]
    path_config = [{
      values = []
    }]
    rule_condition_type = null
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
variable "accelerator_id" {
  description = "(required)"
  type        = string
}

variable "forwarding_rule_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listener_id" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rule_actions" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      forward_group_config = set(object(
        {
          server_group_tuples = set(object(
            {
              endpoint_group_id = string
            }
          ))
        }
      ))
      order            = number
      rule_action_type = string
    }
  ))
}

variable "rule_conditions" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      host_config = set(object(
        {
          values = list(string)
        }
      ))
      path_config = set(object(
        {
          values = list(string)
        }
      ))
      rule_condition_type = string
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
resource "alicloud_ga_forwarding_rule" "this" {
  # accelerator_id - (required) is a type of string
  accelerator_id = var.accelerator_id
  # forwarding_rule_name - (optional) is a type of string
  forwarding_rule_name = var.forwarding_rule_name
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # priority - (optional) is a type of number
  priority = var.priority

  dynamic "rule_actions" {
    for_each = var.rule_actions
    content {
      # order - (required) is a type of number
      order = rule_actions.value["order"]
      # rule_action_type - (required) is a type of string
      rule_action_type = rule_actions.value["rule_action_type"]

      dynamic "forward_group_config" {
        for_each = rule_actions.value.forward_group_config
        content {

          dynamic "server_group_tuples" {
            for_each = forward_group_config.value.server_group_tuples
            content {
              # endpoint_group_id - (required) is a type of string
              endpoint_group_id = server_group_tuples.value["endpoint_group_id"]
            }
          }

        }
      }

    }
  }

  dynamic "rule_conditions" {
    for_each = var.rule_conditions
    content {
      # rule_condition_type - (required) is a type of string
      rule_condition_type = rule_conditions.value["rule_condition_type"]

      dynamic "host_config" {
        for_each = rule_conditions.value.host_config
        content {
          # values - (optional) is a type of list of string
          values = host_config.value["values"]
        }
      }

      dynamic "path_config" {
        for_each = rule_conditions.value.path_config
        content {
          # values - (optional) is a type of list of string
          values = path_config.value["values"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "forwarding_rule_id" {
  description = "returns a string"
  value       = alicloud_ga_forwarding_rule.this.forwarding_rule_id
}

output "forwarding_rule_status" {
  description = "returns a string"
  value       = alicloud_ga_forwarding_rule.this.forwarding_rule_status
}

output "id" {
  description = "returns a string"
  value       = alicloud_ga_forwarding_rule.this.id
}

output "priority" {
  description = "returns a number"
  value       = alicloud_ga_forwarding_rule.this.priority
}

output "this" {
  value = alicloud_ga_forwarding_rule.this
}
```

[top](#index)