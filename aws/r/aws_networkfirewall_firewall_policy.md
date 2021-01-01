# aws_networkfirewall_firewall_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_networkfirewall_firewall_policy" {
  source = "./modules/aws/r/aws_networkfirewall_firewall_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  firewall_policy = [{
    stateful_rule_group_reference = [{
      resource_arn = null
    }]
    stateless_custom_action = [{
      action_definition = [{
        publish_metric_action = [{
          dimension = [{
            value = null
          }]
        }]
      }]
      action_name = null
    }]
    stateless_default_actions          = []
    stateless_fragment_default_actions = []
    stateless_rule_group_reference = [{
      priority     = null
      resource_arn = null
    }]
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "firewall_policy" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      stateful_rule_group_reference = set(object(
        {
          resource_arn = string
        }
      ))
      stateless_custom_action = set(object(
        {
          action_definition = list(object(
            {
              publish_metric_action = list(object(
                {
                  dimension = set(object(
                    {
                      value = string
                    }
                  ))
                }
              ))
            }
          ))
          action_name = string
        }
      ))
      stateless_default_actions          = set(string)
      stateless_fragment_default_actions = set(string)
      stateless_rule_group_reference = set(object(
        {
          priority     = number
          resource_arn = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_networkfirewall_firewall_policy" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags

  dynamic "firewall_policy" {
    for_each = var.firewall_policy
    content {
      stateless_default_actions          = firewall_policy.value["stateless_default_actions"]
      stateless_fragment_default_actions = firewall_policy.value["stateless_fragment_default_actions"]

      dynamic "stateful_rule_group_reference" {
        for_each = firewall_policy.value.stateful_rule_group_reference
        content {
          resource_arn = stateful_rule_group_reference.value["resource_arn"]
        }
      }

      dynamic "stateless_custom_action" {
        for_each = firewall_policy.value.stateless_custom_action
        content {
          action_name = stateless_custom_action.value["action_name"]

          dynamic "action_definition" {
            for_each = stateless_custom_action.value.action_definition
            content {

              dynamic "publish_metric_action" {
                for_each = action_definition.value.publish_metric_action
                content {

                  dynamic "dimension" {
                    for_each = publish_metric_action.value.dimension
                    content {
                      value = dimension.value["value"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "stateless_rule_group_reference" {
        for_each = firewall_policy.value.stateless_rule_group_reference
        content {
          priority     = stateless_rule_group_reference.value["priority"]
          resource_arn = stateless_rule_group_reference.value["resource_arn"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_networkfirewall_firewall_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_networkfirewall_firewall_policy.this.id
}

output "update_token" {
  description = "returns a string"
  value       = aws_networkfirewall_firewall_policy.this.update_token
}

output "this" {
  value = aws_networkfirewall_firewall_policy.this
}
```

[top](#index)