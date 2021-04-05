# google_app_engine_firewall_rule

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_app_engine_firewall_rule" {
  source = "./modules/google-beta/r/google_app_engine_firewall_rule"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # priority - (optional) is a type of number
  priority = null
  # project - (optional) is a type of string
  project = null
  # source_range - (required) is a type of string
  source_range = null

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
  description = "(required) - The action to take if this rule matches. Possible values: [\"UNSPECIFIED_ACTION\", \"ALLOW\", \"DENY\"]"
  type        = string
}

variable "description" {
  description = "(optional) - An optional string description of this rule."
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional) - A positive integer that defines the order of rule evaluation.\nRules with the lowest priority are evaluated first.\n\nA default rule at priority Int32.MaxValue matches all IPv4 and\nIPv6 traffic when no previous rule matches. Only the action of\nthis rule can be modified by the user."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_range" {
  description = "(required) - IP address or range, defined using CIDR notation, of requests that this rule applies to."
  type        = string
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
resource "google_app_engine_firewall_rule" "this" {
  action       = var.action
  description  = var.description
  priority     = var.priority
  project      = var.project
  source_range = var.source_range

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
  value       = google_app_engine_firewall_rule.this.id
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_firewall_rule.this.project
}

output "this" {
  value = google_app_engine_firewall_rule.this
}
```

[top](#index)