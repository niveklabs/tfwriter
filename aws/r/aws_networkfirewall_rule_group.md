# aws_networkfirewall_rule_group

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

```terraform
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
  description = "nested block: NestingList, min items: 0, max items: 1"
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

```terraform
resource "aws_networkfirewall_rule_group" "this" {
  # capacity - (required) is a type of number
  capacity = var.capacity
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # rules - (optional) is a type of string
  rules = var.rules
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type

  dynamic "rule_group" {
    for_each = var.rule_group
    content {

      dynamic "rule_variables" {
        for_each = rule_group.value.rule_variables
        content {

          dynamic "ip_sets" {
            for_each = rule_variables.value.ip_sets
            content {
              # key - (required) is a type of string
              key = ip_sets.value["key"]

              dynamic "ip_set" {
                for_each = ip_sets.value.ip_set
                content {
                  # definition - (required) is a type of set of string
                  definition = ip_set.value["definition"]
                }
              }

            }
          }

          dynamic "port_sets" {
            for_each = rule_variables.value.port_sets
            content {
              # key - (required) is a type of string
              key = port_sets.value["key"]

              dynamic "port_set" {
                for_each = port_sets.value.port_set
                content {
                  # definition - (required) is a type of set of string
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
          # rules_string - (optional) is a type of string
          rules_string = rules_source.value["rules_string"]

          dynamic "rules_source_list" {
            for_each = rules_source.value.rules_source_list
            content {
              # generated_rules_type - (required) is a type of string
              generated_rules_type = rules_source_list.value["generated_rules_type"]
              # target_types - (required) is a type of set of string
              target_types = rules_source_list.value["target_types"]
              # targets - (required) is a type of set of string
              targets = rules_source_list.value["targets"]
            }
          }

          dynamic "stateful_rule" {
            for_each = rules_source.value.stateful_rule
            content {
              # action - (required) is a type of string
              action = stateful_rule.value["action"]

              dynamic "header" {
                for_each = stateful_rule.value.header
                content {
                  # destination - (required) is a type of string
                  destination = header.value["destination"]
                  # destination_port - (required) is a type of string
                  destination_port = header.value["destination_port"]
                  # direction - (required) is a type of string
                  direction = header.value["direction"]
                  # protocol - (required) is a type of string
                  protocol = header.value["protocol"]
                  # source - (required) is a type of string
                  source = header.value["source"]
                  # source_port - (required) is a type of string
                  source_port = header.value["source_port"]
                }
              }

              dynamic "rule_option" {
                for_each = stateful_rule.value.rule_option
                content {
                  # keyword - (required) is a type of string
                  keyword = rule_option.value["keyword"]
                  # settings - (optional) is a type of set of string
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
                  # action_name - (required) is a type of string
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
                              # value - (required) is a type of string
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
                  # priority - (required) is a type of number
                  priority = stateless_rule.value["priority"]

                  dynamic "rule_definition" {
                    for_each = stateless_rule.value.rule_definition
                    content {
                      # actions - (required) is a type of set of string
                      actions = rule_definition.value["actions"]

                      dynamic "match_attributes" {
                        for_each = rule_definition.value.match_attributes
                        content {
                          # protocols - (optional) is a type of set of number
                          protocols = match_attributes.value["protocols"]

                          dynamic "destination" {
                            for_each = match_attributes.value.destination
                            content {
                              # address_definition - (required) is a type of string
                              address_definition = destination.value["address_definition"]
                            }
                          }

                          dynamic "destination_port" {
                            for_each = match_attributes.value.destination_port
                            content {
                              # from_port - (required) is a type of number
                              from_port = destination_port.value["from_port"]
                              # to_port - (optional) is a type of number
                              to_port = destination_port.value["to_port"]
                            }
                          }

                          dynamic "source" {
                            for_each = match_attributes.value.source
                            content {
                              # address_definition - (required) is a type of string
                              address_definition = source.value["address_definition"]
                            }
                          }

                          dynamic "source_port" {
                            for_each = match_attributes.value.source_port
                            content {
                              # from_port - (required) is a type of number
                              from_port = source_port.value["from_port"]
                              # to_port - (optional) is a type of number
                              to_port = source_port.value["to_port"]
                            }
                          }

                          dynamic "tcp_flag" {
                            for_each = match_attributes.value.tcp_flag
                            content {
                              # flags - (required) is a type of set of string
                              flags = tcp_flag.value["flags"]
                              # masks - (optional) is a type of set of string
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

```terraform
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