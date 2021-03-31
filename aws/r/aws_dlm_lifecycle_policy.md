# aws_dlm_lifecycle_policy

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_dlm_lifecycle_policy" {
  source = "./modules/aws/r/aws_dlm_lifecycle_policy"

  # description - (required) is a type of string
  description = null
  # execution_role_arn - (required) is a type of string
  execution_role_arn = null
  # state - (optional) is a type of string
  state = null
  # tags - (optional) is a type of map of string
  tags = {}

  policy_details = [{
    resource_types = []
    schedule = [{
      copy_tags = null
      create_rule = [{
        interval      = null
        interval_unit = null
        times         = []
      }]
      name = null
      retain_rule = [{
        count = null
      }]
      tags_to_add = {}
    }]
    target_tags = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "execution_role_arn" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "policy_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      resource_types = list(string)
      schedule = list(object(
        {
          copy_tags = bool
          create_rule = list(object(
            {
              interval      = number
              interval_unit = string
              times         = list(string)
            }
          ))
          name = string
          retain_rule = list(object(
            {
              count = number
            }
          ))
          tags_to_add = map(string)
        }
      ))
      target_tags = map(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_dlm_lifecycle_policy" "this" {
  description        = var.description
  execution_role_arn = var.execution_role_arn
  state              = var.state
  tags               = var.tags

  dynamic "policy_details" {
    for_each = var.policy_details
    content {
      resource_types = policy_details.value["resource_types"]
      target_tags    = policy_details.value["target_tags"]

      dynamic "schedule" {
        for_each = policy_details.value.schedule
        content {
          copy_tags   = schedule.value["copy_tags"]
          name        = schedule.value["name"]
          tags_to_add = schedule.value["tags_to_add"]

          dynamic "create_rule" {
            for_each = schedule.value.create_rule
            content {
              interval      = create_rule.value["interval"]
              interval_unit = create_rule.value["interval_unit"]
              times         = create_rule.value["times"]
            }
          }

          dynamic "retain_rule" {
            for_each = schedule.value.retain_rule
            content {
              count = retain_rule.value["count"]
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
output "arn" {
  description = "returns a string"
  value       = aws_dlm_lifecycle_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_dlm_lifecycle_policy.this.id
}

output "this" {
  value = aws_dlm_lifecycle_policy.this
}
```

[top](#index)