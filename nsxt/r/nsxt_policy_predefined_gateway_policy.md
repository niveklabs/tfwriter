# nsxt_policy_predefined_gateway_policy

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
module "nsxt_policy_predefined_gateway_policy" {
  source = "./modules/nsxt/r/nsxt_policy_predefined_gateway_policy"

  # description - (optional) is a type of string
  description = null
  # path - (required) is a type of string
  path = null

  default_rule = [{
    action          = null
    description     = null
    log_label       = null
    logged          = null
    nsx_id          = null
    path            = null
    revision        = null
    scope           = null
    sequence_number = null
    tag = [{
      scope = null
      tag   = null
    }]
  }]

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
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "path" {
  description = "(required) - Path for this Gateway Policy"
  type        = string
}

variable "default_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action          = string
      description     = string
      log_label       = string
      logged          = bool
      nsx_id          = string
      path            = string
      revision        = number
      scope           = string
      sequence_number = number
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
resource "nsxt_policy_predefined_gateway_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # path - (required) is a type of string
  path = var.path

  dynamic "default_rule" {
    for_each = var.default_rule
    content {
      # action - (optional) is a type of string
      action = default_rule.value["action"]
      # description - (optional) is a type of string
      description = default_rule.value["description"]
      # log_label - (optional) is a type of string
      log_label = default_rule.value["log_label"]
      # logged - (optional) is a type of bool
      logged = default_rule.value["logged"]
      # scope - (required) is a type of string
      scope = default_rule.value["scope"]

      dynamic "tag" {
        for_each = default_rule.value.tag
        content {
          # scope - (optional) is a type of string
          scope = tag.value["scope"]
          # tag - (optional) is a type of string
          tag = tag.value["tag"]
        }
      }

    }
  }

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
      # scope - (required) is a type of set of string
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
output "description" {
  description = "returns a string"
  value       = nsxt_policy_predefined_gateway_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = nsxt_policy_predefined_gateway_policy.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_predefined_gateway_policy.this.revision
}

output "this" {
  value = nsxt_policy_predefined_gateway_policy.this
}
```

[top](#index)