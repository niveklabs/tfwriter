# oci_autoscaling_auto_scaling_configuration

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_autoscaling_auto_scaling_configuration" {
  source = "./modules/oci/r/oci_autoscaling_auto_scaling_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cool_down_in_seconds - (optional) is a type of number
  cool_down_in_seconds = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_enabled - (optional) is a type of bool
  is_enabled = null

  auto_scaling_resources = [{
    id   = null
    type = null
  }]

  policies = [{
    capacity = [{
      initial = null
      max     = null
      min     = null
    }]
    display_name = null
    execution_schedule = [{
      expression = null
      timezone   = null
      type       = null
    }]
    id          = null
    is_enabled  = null
    policy_type = null
    resource_action = [{
      action      = null
      action_type = null
    }]
    rules = [{
      action = [{
        type  = null
        value = null
      }]
      display_name = null
      id           = null
      metric = [{
        metric_type = null
        threshold = [{
          operator = null
          value    = null
        }]
      }]
    }]
    time_created = null
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

variable "cool_down_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_scaling_resources" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      id   = string
      type = string
    }
  ))
}

variable "policies" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      capacity = list(object(
        {
          initial = number
          max     = number
          min     = number
        }
      ))
      display_name = string
      execution_schedule = list(object(
        {
          expression = string
          timezone   = string
          type       = string
        }
      ))
      id          = string
      is_enabled  = bool
      policy_type = string
      resource_action = list(object(
        {
          action      = string
          action_type = string
        }
      ))
      rules = set(object(
        {
          action = list(object(
            {
              type  = string
              value = number
            }
          ))
          display_name = string
          id           = string
          metric = list(object(
            {
              metric_type = string
              threshold = list(object(
                {
                  operator = string
                  value    = number
                }
              ))
            }
          ))
        }
      ))
      time_created = string
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
resource "oci_autoscaling_auto_scaling_configuration" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # cool_down_in_seconds - (optional) is a type of number
  cool_down_in_seconds = var.cool_down_in_seconds
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled

  dynamic "auto_scaling_resources" {
    for_each = var.auto_scaling_resources
    content {
      # id - (required) is a type of string
      id = auto_scaling_resources.value["id"]
      # type - (required) is a type of string
      type = auto_scaling_resources.value["type"]
    }
  }

  dynamic "policies" {
    for_each = var.policies
    content {
      # display_name - (optional) is a type of string
      display_name = policies.value["display_name"]
      # is_enabled - (optional) is a type of bool
      is_enabled = policies.value["is_enabled"]
      # policy_type - (required) is a type of string
      policy_type = policies.value["policy_type"]

      dynamic "capacity" {
        for_each = policies.value.capacity
        content {
          # initial - (optional) is a type of number
          initial = capacity.value["initial"]
          # max - (optional) is a type of number
          max = capacity.value["max"]
          # min - (optional) is a type of number
          min = capacity.value["min"]
        }
      }

      dynamic "execution_schedule" {
        for_each = policies.value.execution_schedule
        content {
          # expression - (required) is a type of string
          expression = execution_schedule.value["expression"]
          # timezone - (required) is a type of string
          timezone = execution_schedule.value["timezone"]
          # type - (required) is a type of string
          type = execution_schedule.value["type"]
        }
      }

      dynamic "resource_action" {
        for_each = policies.value.resource_action
        content {
          # action - (required) is a type of string
          action = resource_action.value["action"]
          # action_type - (required) is a type of string
          action_type = resource_action.value["action_type"]
        }
      }

      dynamic "rules" {
        for_each = policies.value.rules
        content {
          # display_name - (required) is a type of string
          display_name = rules.value["display_name"]

          dynamic "action" {
            for_each = rules.value.action
            content {
              # type - (optional) is a type of string
              type = action.value["type"]
              # value - (optional) is a type of number
              value = action.value["value"]
            }
          }

          dynamic "metric" {
            for_each = rules.value.metric
            content {
              # metric_type - (optional) is a type of string
              metric_type = metric.value["metric_type"]

              dynamic "threshold" {
                for_each = metric.value.threshold
                content {
                  # operator - (optional) is a type of string
                  operator = threshold.value["operator"]
                  # value - (optional) is a type of number
                  value = threshold.value["value"]
                }
              }

            }
          }

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
output "cool_down_in_seconds" {
  description = "returns a number"
  value       = oci_autoscaling_auto_scaling_configuration.this.cool_down_in_seconds
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_autoscaling_auto_scaling_configuration.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_autoscaling_auto_scaling_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_autoscaling_auto_scaling_configuration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_autoscaling_auto_scaling_configuration.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = oci_autoscaling_auto_scaling_configuration.this.is_enabled
}

output "max_resource_count" {
  description = "returns a number"
  value       = oci_autoscaling_auto_scaling_configuration.this.max_resource_count
}

output "min_resource_count" {
  description = "returns a number"
  value       = oci_autoscaling_auto_scaling_configuration.this.min_resource_count
}

output "time_created" {
  description = "returns a string"
  value       = oci_autoscaling_auto_scaling_configuration.this.time_created
}

output "this" {
  value = oci_autoscaling_auto_scaling_configuration.this
}
```

[top](#index)