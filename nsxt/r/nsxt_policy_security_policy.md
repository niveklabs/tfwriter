# nsxt_policy_security_policy

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_security_policy" {
  source = "./modules/nsxt/r/nsxt_policy_security_policy"

  # category - (required) is a type of string
  category = null
  # comments - (optional) is a type of string
  comments = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # locked - (optional) is a type of bool
  locked = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # scope - (optional) is a type of set of string
  scope = []
  # sequence_number - (optional) is a type of number
  sequence_number = null
  # stateful - (optional) is a type of bool
  stateful = null
  # tcp_strict - (optional) is a type of bool
  tcp_strict = null

  rule = [{
    action                = null
    description           = null
    destination_groups    = []
    destinations_excluded = null
    direction             = null
    disabled              = null
    display_name          = null
    ip_version            = null
    log_label             = null
    logged                = null
    notes                 = null
    nsx_id                = null
    profiles              = []
    revision              = null
    rule_id               = null
    scope                 = []
    sequence_number       = null
    services              = []
    source_groups         = []
    sources_excluded      = null
    tag = [{
      scope = null
      tag   = null
    }]
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(required) - Category"
  type        = string
}

variable "comments" {
  description = "(optional) - Comments for security policy lock/unlock"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "domain" {
  description = "(optional) - The domain name to use for resources. If not specified 'default' is used"
  type        = string
  default     = null
}

variable "locked" {
  description = "(optional) - Indicates whether a security policy should be locked. If locked by a user, no other user would be able to modify this policy"
  type        = bool
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional) - The list of group paths where the rules in this policy will get applied"
  type        = set(string)
  default     = null
}

variable "sequence_number" {
  description = "(optional) - This field is used to resolve conflicts between security policies across domains"
  type        = number
  default     = null
}

variable "stateful" {
  description = "(optional) - When it is stateful, the state of the network connects are tracked and a stateful packet inspection is performed"
  type        = bool
  default     = null
}

variable "tcp_strict" {
  description = "(optional) - Ensures that a 3 way TCP handshake is done before the data packets are sent"
  type        = bool
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 1000"
  type = set(object(
    {
      action                = string
      description           = string
      destination_groups    = set(string)
      destinations_excluded = bool
      direction             = string
      disabled              = bool
      display_name          = string
      ip_version            = string
      log_label             = string
      logged                = bool
      notes                 = string
      nsx_id                = string
      profiles              = set(string)
      revision              = number
      rule_id               = number
      scope                 = set(string)
      sequence_number       = number
      services              = set(string)
      source_groups         = set(string)
      sources_excluded      = bool
      tag = set(object(
        {
          scope = string
          tag   = string
        }
      ))
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_security_policy" "this" {
  # category - (required) is a type of string
  category = var.category
  # comments - (optional) is a type of string
  comments = var.comments
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # domain - (optional) is a type of string
  domain = var.domain
  # locked - (optional) is a type of bool
  locked = var.locked
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # scope - (optional) is a type of set of string
  scope = var.scope
  # sequence_number - (optional) is a type of number
  sequence_number = var.sequence_number
  # stateful - (optional) is a type of bool
  stateful = var.stateful
  # tcp_strict - (optional) is a type of bool
  tcp_strict = var.tcp_strict

  dynamic "rule" {
    for_each = var.rule
    content {
      # action - (optional) is a type of string
      action = rule.value["action"]
      # description - (optional) is a type of string
      description = rule.value["description"]
      # destination_groups - (optional) is a type of set of string
      destination_groups = rule.value["destination_groups"]
      # destinations_excluded - (optional) is a type of bool
      destinations_excluded = rule.value["destinations_excluded"]
      # direction - (optional) is a type of string
      direction = rule.value["direction"]
      # disabled - (optional) is a type of bool
      disabled = rule.value["disabled"]
      # display_name - (required) is a type of string
      display_name = rule.value["display_name"]
      # ip_version - (optional) is a type of string
      ip_version = rule.value["ip_version"]
      # log_label - (optional) is a type of string
      log_label = rule.value["log_label"]
      # logged - (optional) is a type of bool
      logged = rule.value["logged"]
      # notes - (optional) is a type of string
      notes = rule.value["notes"]
      # nsx_id - (optional) is a type of string
      nsx_id = rule.value["nsx_id"]
      # profiles - (optional) is a type of set of string
      profiles = rule.value["profiles"]
      # scope - (optional) is a type of set of string
      scope = rule.value["scope"]
      # sequence_number - (optional) is a type of number
      sequence_number = rule.value["sequence_number"]
      # services - (optional) is a type of set of string
      services = rule.value["services"]
      # source_groups - (optional) is a type of set of string
      source_groups = rule.value["source_groups"]
      # sources_excluded - (optional) is a type of bool
      sources_excluded = rule.value["sources_excluded"]

      dynamic "tag" {
        for_each = rule.value.tag
        content {
          # scope - (optional) is a type of string
          scope = tag.value["scope"]
          # tag - (optional) is a type of string
          tag = tag.value["tag"]
        }
      }

    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_security_policy.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_security_policy.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_security_policy.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_security_policy.this.revision
}

output "tcp_strict" {
  description = "returns a bool"
  value       = nsxt_policy_security_policy.this.tcp_strict
}

output "this" {
  value = nsxt_policy_security_policy.this
}
```

[top](#index)