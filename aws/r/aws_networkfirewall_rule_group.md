# aws_networkfirewall_rule_group
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_networkfirewall_rule_group" {
  source = "./modules/aws/r/aws_networkfirewall_rule_group"

  # capacity - (required) is a type of number
  capacity = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # rules - (optional) is a type of string
  rules = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null

  rule_group = [{
    rule_variables = [{
      ip_sets = [{
        ip_set = [{
          definition = []
        }]
        key = null
      }]
      port_sets = [{
        key = null
        port_set = [{
          definition = []
        }]
      }]
    }]
    rules_source = [{
      rules_source_list = [{
        generated_rules_type = null
        target_types         = []
        targets              = []
      }]
      rules_string = null
      stateful_rule = [{
        action = null
        header = [{
          destination      = null
          destination_port = null
          direction        = null
          protocol         = null
          source           = null
          source_port      = null
        }]
        rule_option = [{
          keyword  = null
          settings = []
        }]
      }]
      stateless_rules_and_custom_actions = [{
        custom_action = [{
          action_definition = [{
            publish_metric_action = [{
              dimension = [{
                value = null
              }]
            }]
          }]
          action_name = null
        }]
        stateless_rule = [{
          priority = null
          rule_definition = [{
            actions = []
            match_attributes = [{
              destination = [{
                address_definition = null
              }]
              destination_port = [{
                from_port = null
                to_port   = null
              }]
              protocols = []
              source = [{
                address_definition = null
              }]
              source_port = [{
                from_port = null
                to_port   = null
              }]
              tcp_flag = [{
                flags = []
                masks = []
              }]
            }]
          }]
        }]
      }]
    }]
  }]
}
```
[top](#index)
### Variables
```hcl
variable "capacity" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rules" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "rule_group" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      rule_variables = list(object(
        {
          ip_sets = set(object(
            {
              ip_set = list(object(
                {
                  definition = set(string)
                }
              ))
              key = string
            }
          ))
          port_sets = set(object(
            {
              key = string
              port_set = list(object(
                {
                  definition = set(string)
                }
              ))
            }
          ))
        }
      ))
      rules_source = list(object(
        {
          rules_source_list = list(object(
            {
              generated_rules_type = string
              target_types         = set(string)
              targets              = set(string)
            }
          ))
          rules_string = string
          stateful_rule = set(object(
            {
              action = string
              header = list(object(
                {
                  destination      = string
                  destination_port = string
                  direction        = string
                  protocol         = string
                  source           = string
                  source_port      = string
                }
              ))
              rule_option = set(object(
                {
                  keyword  = string
                  settings = set(string)
                }
              ))
            }
          ))
          stateless_rules_and_custom_actions = list(object(
            {
              custom_action = set(object(
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
              stateless_rule = set(object(
                {
                  priority = number
                  rule_definition = list(object(
                    {
                      actions = set(string)
                      match_attributes = list(object(
                        {
                          destination = set(object(
                            {
                              address_definition = string
                            }
                          ))
                          destination_port = set(object(
                            {
                              from_port = number
                              to_port   = number
                            }
                          ))
                          protocols = set(number)
                          source = set(object(
                            {
                              address_definition = string
                            }
                          ))
                          source_port = set(object(
                            {
                              from_port = number
                              to_port   = number
                            }
                          ))
                          tcp_flag = set(object(
                            {
                              flags = set(string)
                              masks = set(string)
                            }
                          ))
                        }
                      ))
                    }
                  ))
                }
              ))
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
```hcl
resource "aws_networkfirewall_rule_group" "this" {
  capacity    = var.capacity
  description = var.description
  name        = var.name
  rules       = var.rules
  tags        = var.tags
  type        = var.type

  dynamic "rule_group" {
    for_each = var.rule_group
    content {

      dynamic "rule_variables" {
        for_each = rule_group.value.rule_variables
        content {

          dynamic "ip_sets" {
            for_each = rule_variables.value.ip_sets
            content {
              key = ip_sets.value["key"]

              dynamic "ip_set" {
                for_each = ip_sets.value.ip_set
                content {
                  definition = ip_set.value["definition"]
                }
              }

            }
          }

          dynamic "port_sets" {
            for_each = rule_variables.value.port_sets
            content {
              key = port_sets.value["key"]

              dynamic "port_set" {
                for_each = port_sets.value.port_set
                content {
                  definition = port_set.value["definition"]
                }
              }

            }
          }

        }
      }

      dynamic "rules_source" {
        for_each = rule_group.value.rules_source
        content {
          rules_string = rules_source.value["rules_string"]

          dynamic "rules_source_list" {
            for_each = rules_source.value.rules_source_list
            content {
              generated_rules_type = rules_source_list.value["generated_rules_type"]
              target_types         = rules_source_list.value["target_types"]
              targets              = rules_source_list.value["targets"]
            }
          }

          dynamic "stateful_rule" {
            for_each = rules_source.value.stateful_rule
            content {
              action = stateful_rule.value["action"]

              dynamic "header" {
                for_each = stateful_rule.value.header
                content {
                  destination      = header.value["destination"]
                  destination_port = header.value["destination_port"]
                  direction        = header.value["direction"]
                  protocol         = header.value["protocol"]
                  source           = header.value["source"]
                  source_port      = header.value["source_port"]
                }
              }

              dynamic "rule_option" {
                for_each = stateful_rule.value.rule_option
                content {
                  keyword  = rule_option.value["keyword"]
                  settings = rule_option.value["settings"]
                }
              }

            }
          }

          dynamic "stateless_rules_and_custom_actions" {
            for_each = rules_source.value.stateless_rules_and_custom_actions
            content {

              dynamic "custom_action" {
                for_each = stateless_rules_and_custom_actions.value.custom_action
                content {
                  action_name = custom_action.value["action_name"]

                  dynamic "action_definition" {
                    for_each = custom_action.value.action_definition
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

              dynamic "stateless_rule" {
                for_each = stateless_rules_and_custom_actions.value.stateless_rule
                content {
                  priority = stateless_rule.value["priority"]

                  dynamic "rule_definition" {
                    for_each = stateless_rule.value.rule_definition
                    content {
                      actions = rule_definition.value["actions"]

                      dynamic "match_attributes" {
                        for_each = rule_definition.value.match_attributes
                        content {
                          protocols = match_attributes.value["protocols"]

                          dynamic "destination" {
                            for_each = match_attributes.value.destination
                            content {
                              address_definition = destination.value["address_definition"]
                            }
                          }

                          dynamic "destination_port" {
                            for_each = match_attributes.value.destination_port
                            content {
                              from_port = destination_port.value["from_port"]
                              to_port   = destination_port.value["to_port"]
                            }
                          }

                          dynamic "source" {
                            for_each = match_attributes.value.source
                            content {
                              address_definition = source.value["address_definition"]
                            }
                          }

                          dynamic "source_port" {
                            for_each = match_attributes.value.source_port
                            content {
                              from_port = source_port.value["from_port"]
                              to_port   = source_port.value["to_port"]
                            }
                          }

                          dynamic "tcp_flag" {
                            for_each = match_attributes.value.tcp_flag
                            content {
                              flags = tcp_flag.value["flags"]
                              masks = tcp_flag.value["masks"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

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
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_networkfirewall_rule_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_networkfirewall_rule_group.this.id
}

output "update_token" {
  description = "returns a string"
  value       = aws_networkfirewall_rule_group.this.update_token
}

output "this" {
  value = aws_networkfirewall_rule_group.this
}
```
[top](#index)
