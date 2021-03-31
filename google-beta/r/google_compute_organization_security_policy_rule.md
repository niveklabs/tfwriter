# google_compute_organization_security_policy_rule

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_organization_security_policy_rule" {
  source = "./modules/google-beta/r/google_compute_organization_security_policy_rule"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # direction - (optional) is a type of string
  direction = null
  # enable_logging - (optional) is a type of bool
  enable_logging = null
  # policy_id - (required) is a type of string
  policy_id = null
  # preview - (optional) is a type of bool
  preview = null
  # priority - (required) is a type of number
  priority = null
  # target_resources - (optional) is a type of list of string
  target_resources = []
  # target_service_accounts - (optional) is a type of list of string
  target_service_accounts = []

  match = [{
    config = [{
      dest_ip_ranges = []
      layer4_config = [{
        ip_protocol = null
        ports       = []
      }]
      src_ip_ranges = []
    }]
    description    = null
    versioned_expr = null
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
variable "action" {
  description = "(required) - The Action to perform when the client connection triggers the rule. Can currently be either\n\"allow\", \"deny\" or \"goto_next\"."
  type        = string
}

variable "description" {
  description = "(optional) - A description of the rule."
  type        = string
  default     = null
}

variable "direction" {
  description = "(optional) - The direction in which this rule applies. If unspecified an INGRESS rule is created. Possible values: [\"INGRESS\", \"EGRESS\"]"
  type        = string
  default     = null
}

variable "enable_logging" {
  description = "(optional) - Denotes whether to enable logging for a particular rule.\nIf logging is enabled, logs will be exported to the\nconfigured export destination in Stackdriver."
  type        = bool
  default     = null
}

variable "policy_id" {
  description = "(required) - The ID of the OrganizationSecurityPolicy this rule applies to."
  type        = string
}

variable "preview" {
  description = "(optional) - If set to true, the specified action is not enforced."
  type        = bool
  default     = null
}

variable "priority" {
  description = "(required) - An integer indicating the priority of a rule in the list. The priority must be a value\nbetween 0 and 2147483647. Rules are evaluated from highest to lowest priority where 0 is the\nhighest priority and 2147483647 is the lowest prority."
  type        = number
}

variable "target_resources" {
  description = "(optional) - A list of network resource URLs to which this rule applies.\nThis field allows you to control which network's VMs get\nthis rule. If this field is left blank, all VMs\nwithin the organization will receive the rule."
  type        = list(string)
  default     = null
}

variable "target_service_accounts" {
  description = "(optional) - A list of service accounts indicating the sets of\ninstances that are applied with this rule."
  type        = list(string)
  default     = null
}

variable "match" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      config = list(object(
        {
          dest_ip_ranges = list(string)
          layer4_config = list(object(
            {
              ip_protocol = string
              ports       = list(string)
            }
          ))
          src_ip_ranges = list(string)
        }
      ))
      description    = string
      versioned_expr = string
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
resource "google_compute_organization_security_policy_rule" "this" {
  action                  = var.action
  description             = var.description
  direction               = var.direction
  enable_logging          = var.enable_logging
  policy_id               = var.policy_id
  preview                 = var.preview
  priority                = var.priority
  target_resources        = var.target_resources
  target_service_accounts = var.target_service_accounts

  dynamic "match" {
    for_each = var.match
    content {
      description    = match.value["description"]
      versioned_expr = match.value["versioned_expr"]

      dynamic "config" {
        for_each = match.value.config
        content {
          dest_ip_ranges = config.value["dest_ip_ranges"]
          src_ip_ranges  = config.value["src_ip_ranges"]

          dynamic "layer4_config" {
            for_each = config.value.layer4_config
            content {
              ip_protocol = layer4_config.value["ip_protocol"]
              ports       = layer4_config.value["ports"]
            }
          }

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
output "id" {
  description = "returns a string"
  value       = google_compute_organization_security_policy_rule.this.id
}

output "this" {
  value = google_compute_organization_security_policy_rule.this
}
```

[top](#index)