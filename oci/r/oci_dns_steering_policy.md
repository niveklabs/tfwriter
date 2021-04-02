# oci_dns_steering_policy

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_steering_policy" {
  source = "./modules/oci/r/oci_dns_steering_policy"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # health_check_monitor_id - (optional) is a type of string
  health_check_monitor_id = null
  # template - (required) is a type of string
  template = null
  # ttl - (optional) is a type of number
  ttl = null

  answers = [{
    is_disabled = null
    name        = null
    pool        = null
    rdata       = null
    rtype       = null
  }]

  rules = [{
    cases = [{
      answer_data = [{
        answer_condition = null
        should_keep      = null
        value            = null
      }]
      case_condition = null
      count          = null
    }]
    default_answer_data = [{
      answer_condition = null
      should_keep      = null
      value            = null
    }]
    default_count = null
    description   = null
    rule_type     = null
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

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
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

variable "health_check_monitor_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "answers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_disabled = bool
      name        = string
      pool        = string
      rdata       = string
      rtype       = string
    }
  ))
  default = []
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cases = list(object(
        {
          answer_data = list(object(
            {
              answer_condition = string
              should_keep      = bool
              value            = number
            }
          ))
          case_condition = string
          count          = number
        }
      ))
      default_answer_data = list(object(
        {
          answer_condition = string
          should_keep      = bool
          value            = number
        }
      ))
      default_count = number
      description   = string
      rule_type     = string
    }
  ))
  default = []
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
resource "oci_dns_steering_policy" "this" {
  compartment_id          = var.compartment_id
  defined_tags            = var.defined_tags
  display_name            = var.display_name
  freeform_tags           = var.freeform_tags
  health_check_monitor_id = var.health_check_monitor_id
  template                = var.template
  ttl                     = var.ttl

  dynamic "answers" {
    for_each = var.answers
    content {
      is_disabled = answers.value["is_disabled"]
      name        = answers.value["name"]
      pool        = answers.value["pool"]
      rdata       = answers.value["rdata"]
      rtype       = answers.value["rtype"]
    }
  }

  dynamic "rules" {
    for_each = var.rules
    content {
      default_count = rules.value["default_count"]
      description   = rules.value["description"]
      rule_type     = rules.value["rule_type"]

      dynamic "cases" {
        for_each = rules.value.cases
        content {
          case_condition = cases.value["case_condition"]
          count          = cases.value["count"]

          dynamic "answer_data" {
            for_each = cases.value.answer_data
            content {
              answer_condition = answer_data.value["answer_condition"]
              should_keep      = answer_data.value["should_keep"]
              value            = answer_data.value["value"]
            }
          }

        }
      }

      dynamic "default_answer_data" {
        for_each = rules.value.default_answer_data
        content {
          answer_condition = default_answer_data.value["answer_condition"]
          should_keep      = default_answer_data.value["should_keep"]
          value            = default_answer_data.value["value"]
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
  value       = oci_dns_steering_policy.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dns_steering_policy.this.freeform_tags
}

output "health_check_monitor_id" {
  description = "returns a string"
  value       = oci_dns_steering_policy.this.health_check_monitor_id
}

output "id" {
  description = "returns a string"
  value       = oci_dns_steering_policy.this.id
}

output "self" {
  description = "returns a string"
  value       = oci_dns_steering_policy.this.self
}

output "state" {
  description = "returns a string"
  value       = oci_dns_steering_policy.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_steering_policy.this.time_created
}

output "ttl" {
  description = "returns a number"
  value       = oci_dns_steering_policy.this.ttl
}

output "this" {
  value = oci_dns_steering_policy.this
}
```

[top](#index)