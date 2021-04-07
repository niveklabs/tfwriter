# launchdarkly_feature_flag_environment

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_feature_flag_environment" {
  source = "./modules/launchdarkly/r/launchdarkly_feature_flag_environment"

  # env_key - (required) is a type of string
  env_key = null
  # flag_id - (required) is a type of string
  flag_id = null
  # off_variation - (optional) is a type of number
  off_variation = null
  # targeting_enabled - (optional) is a type of bool
  targeting_enabled = null
  # track_events - (optional) is a type of bool
  track_events = null

  flag_fallthrough = [{
    bucket_by       = null
    rollout_weights = []
    variation       = null
  }]

  prerequisites = [{
    flag_key  = null
    variation = null
  }]

  rules = [{
    bucket_by = null
    clauses = [{
      attribute  = null
      negate     = null
      op         = null
      value_type = null
      values     = []
    }]
    rollout_weights = []
    variation       = null
  }]

  user_targets = [{
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "env_key" {
  description = "(required)"
  type        = string
}

variable "flag_id" {
  description = "(required)"
  type        = string
}

variable "off_variation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "targeting_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "track_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "flag_fallthrough" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_by       = string
      rollout_weights = list(number)
      variation       = number
    }
  ))
  default = []
}

variable "prerequisites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      flag_key  = string
      variation = number
    }
  ))
  default = []
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_by = string
      clauses = list(object(
        {
          attribute  = string
          negate     = bool
          op         = string
          value_type = string
          values     = list(string)
        }
      ))
      rollout_weights = list(number)
      variation       = number
    }
  ))
  default = []
}

variable "user_targets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_feature_flag_environment" "this" {
  # env_key - (required) is a type of string
  env_key = var.env_key
  # flag_id - (required) is a type of string
  flag_id = var.flag_id
  # off_variation - (optional) is a type of number
  off_variation = var.off_variation
  # targeting_enabled - (optional) is a type of bool
  targeting_enabled = var.targeting_enabled
  # track_events - (optional) is a type of bool
  track_events = var.track_events

  dynamic "flag_fallthrough" {
    for_each = var.flag_fallthrough
    content {
      # bucket_by - (optional) is a type of string
      bucket_by = flag_fallthrough.value["bucket_by"]
      # rollout_weights - (optional) is a type of list of number
      rollout_weights = flag_fallthrough.value["rollout_weights"]
      # variation - (optional) is a type of number
      variation = flag_fallthrough.value["variation"]
    }
  }

  dynamic "prerequisites" {
    for_each = var.prerequisites
    content {
      # flag_key - (required) is a type of string
      flag_key = prerequisites.value["flag_key"]
      # variation - (required) is a type of number
      variation = prerequisites.value["variation"]
    }
  }

  dynamic "rules" {
    for_each = var.rules
    content {
      # bucket_by - (optional) is a type of string
      bucket_by = rules.value["bucket_by"]
      # rollout_weights - (optional) is a type of list of number
      rollout_weights = rules.value["rollout_weights"]
      # variation - (optional) is a type of number
      variation = rules.value["variation"]

      dynamic "clauses" {
        for_each = rules.value.clauses
        content {
          # attribute - (required) is a type of string
          attribute = clauses.value["attribute"]
          # negate - (required) is a type of bool
          negate = clauses.value["negate"]
          # op - (required) is a type of string
          op = clauses.value["op"]
          # value_type - (optional) is a type of string
          value_type = clauses.value["value_type"]
          # values - (required) is a type of list of string
          values = clauses.value["values"]
        }
      }

    }
  }

  dynamic "user_targets" {
    for_each = var.user_targets
    content {
      # values - (optional) is a type of list of string
      values = user_targets.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = launchdarkly_feature_flag_environment.this.id
}

output "off_variation" {
  description = "returns a number"
  value       = launchdarkly_feature_flag_environment.this.off_variation
}

output "targeting_enabled" {
  description = "returns a bool"
  value       = launchdarkly_feature_flag_environment.this.targeting_enabled
}

output "track_events" {
  description = "returns a bool"
  value       = launchdarkly_feature_flag_environment.this.track_events
}

output "this" {
  value = launchdarkly_feature_flag_environment.this
}
```

[top](#index)