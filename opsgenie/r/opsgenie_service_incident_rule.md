# opsgenie_service_incident_rule

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_service_incident_rule" {
  source = "./modules/opsgenie/r/opsgenie_service_incident_rule"

  # service_id - (required) is a type of string
  service_id = null

  incident_rule = [{
    condition_match_type = null
    conditions = [{
      expected_value = null
      field          = null
      key            = null
      not            = null
      operation      = null
    }]
    incident_properties = [{
      description = null
      details     = {}
      message     = null
      priority    = null
      stakeholder_properties = [{
        description = null
        enable      = null
        message     = null
      }]
      tags = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "service_id" {
  description = "(required)"
  type        = string
}

variable "incident_rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      condition_match_type = string
      conditions = list(object(
        {
          expected_value = string
          field          = string
          key            = string
          not            = bool
          operation      = string
        }
      ))
      incident_properties = list(object(
        {
          description = string
          details     = map(string)
          message     = string
          priority    = string
          stakeholder_properties = list(object(
            {
              description = string
              enable      = bool
              message     = string
            }
          ))
          tags = set(string)
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_service_incident_rule" "this" {
  # service_id - (required) is a type of string
  service_id = var.service_id

  dynamic "incident_rule" {
    for_each = var.incident_rule
    content {
      # condition_match_type - (optional) is a type of string
      condition_match_type = incident_rule.value["condition_match_type"]

      dynamic "conditions" {
        for_each = incident_rule.value.conditions
        content {
          # expected_value - (optional) is a type of string
          expected_value = conditions.value["expected_value"]
          # field - (required) is a type of string
          field = conditions.value["field"]
          # key - (optional) is a type of string
          key = conditions.value["key"]
          # not - (optional) is a type of bool
          not = conditions.value["not"]
          # operation - (required) is a type of string
          operation = conditions.value["operation"]
        }
      }

      dynamic "incident_properties" {
        for_each = incident_rule.value.incident_properties
        content {
          # description - (optional) is a type of string
          description = incident_properties.value["description"]
          # details - (optional) is a type of map of string
          details = incident_properties.value["details"]
          # message - (required) is a type of string
          message = incident_properties.value["message"]
          # priority - (required) is a type of string
          priority = incident_properties.value["priority"]
          # tags - (optional) is a type of set of string
          tags = incident_properties.value["tags"]

          dynamic "stakeholder_properties" {
            for_each = incident_properties.value.stakeholder_properties
            content {
              # description - (optional) is a type of string
              description = stakeholder_properties.value["description"]
              # enable - (optional) is a type of bool
              enable = stakeholder_properties.value["enable"]
              # message - (required) is a type of string
              message = stakeholder_properties.value["message"]
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
output "id" {
  description = "returns a string"
  value       = opsgenie_service_incident_rule.this.id
}

output "this" {
  value = opsgenie_service_incident_rule.this
}
```

[top](#index)