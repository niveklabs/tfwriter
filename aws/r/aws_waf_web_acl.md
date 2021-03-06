# aws_waf_web_acl

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_waf_web_acl" {
  source = "./modules/aws/r/aws_waf_web_acl"

  # metric_name - (required) is a type of string
  metric_name = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  default_action = [{
    type = null
  }]

  logging_configuration = [{
    log_destination = null
    redacted_fields = [{
      field_to_match = [{
        data = null
        type = null
      }]
    }]
  }]

  rules = [{
    action = [{
      type = null
    }]
    override_action = [{
      type = null
    }]
    priority = null
    rule_id  = null
    type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "metric_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "default_action" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
}

variable "logging_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log_destination = string
      redacted_fields = list(object(
        {
          field_to_match = set(object(
            {
              data = string
              type = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          type = string
        }
      ))
      override_action = list(object(
        {
          type = string
        }
      ))
      priority = number
      rule_id  = string
      type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_waf_web_acl" "this" {
  # metric_name - (required) is a type of string
  metric_name = var.metric_name
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "default_action" {
    for_each = var.default_action
    content {
      # type - (required) is a type of string
      type = default_action.value["type"]
    }
  }

  dynamic "logging_configuration" {
    for_each = var.logging_configuration
    content {
      # log_destination - (required) is a type of string
      log_destination = logging_configuration.value["log_destination"]

      dynamic "redacted_fields" {
        for_each = logging_configuration.value.redacted_fields
        content {

          dynamic "field_to_match" {
            for_each = redacted_fields.value.field_to_match
            content {
              # data - (optional) is a type of string
              data = field_to_match.value["data"]
              # type - (required) is a type of string
              type = field_to_match.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "rules" {
    for_each = var.rules
    content {
      # priority - (required) is a type of number
      priority = rules.value["priority"]
      # rule_id - (required) is a type of string
      rule_id = rules.value["rule_id"]
      # type - (optional) is a type of string
      type = rules.value["type"]

      dynamic "action" {
        for_each = rules.value.action
        content {
          # type - (required) is a type of string
          type = action.value["type"]
        }
      }

      dynamic "override_action" {
        for_each = rules.value.override_action
        content {
          # type - (required) is a type of string
          type = override_action.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_waf_web_acl.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_web_acl.this.id
}

output "this" {
  value = aws_waf_web_acl.this
}
```

[top](#index)