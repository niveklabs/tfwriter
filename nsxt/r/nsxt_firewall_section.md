# nsxt_firewall_section

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
module "nsxt_firewall_section" {
  source = "./modules/nsxt/r/nsxt_firewall_section"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # insert_before - (optional) is a type of string
  insert_before = null
  # section_type - (required) is a type of string
  section_type = null
  # stateful - (required) is a type of bool
  stateful = null

  applied_to = [{
    is_valid            = null
    target_display_name = null
    target_id           = null
    target_type         = null
  }]

  rule = [{
    action = null
    applied_to = [{
      is_valid            = null
      target_display_name = null
      target_id           = null
      target_type         = null
    }]
    description = null
    destination = [{
      is_valid            = null
      target_display_name = null
      target_id           = null
      target_type         = null
    }]
    destinations_excluded = null
    direction             = null
    disabled              = null
    display_name          = null
    id                    = null
    ip_protocol           = null
    logged                = null
    notes                 = null
    revision              = null
    rule_tag              = null
    service = [{
      is_valid            = null
      target_display_name = null
      target_id           = null
      target_type         = null
    }]
    source = [{
      is_valid            = null
      target_display_name = null
      target_id           = null
      target_type         = null
    }]
    sources_excluded = null
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
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "insert_before" {
  description = "(optional) - Id of section that should come after this one"
  type        = string
  default     = null
}

variable "section_type" {
  description = "(required) - Type of the rules which a section can contain. Only homogeneous sections are supported"
  type        = string
}

variable "stateful" {
  description = "(required) - Stateful or Stateless nature of firewall section is enforced on all rules inside the section"
  type        = bool
}

variable "applied_to" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      is_valid            = bool
      target_display_name = string
      target_id           = string
      target_type         = string
    }
  ))
  default = []
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      applied_to = set(object(
        {
          is_valid            = bool
          target_display_name = string
          target_id           = string
          target_type         = string
        }
      ))
      description = string
      destination = set(object(
        {
          is_valid            = bool
          target_display_name = string
          target_id           = string
          target_type         = string
        }
      ))
      destinations_excluded = bool
      direction             = string
      disabled              = bool
      display_name          = string
      id                    = string
      ip_protocol           = string
      logged                = bool
      notes                 = string
      revision              = number
      rule_tag              = string
      service = set(object(
        {
          is_valid            = bool
          target_display_name = string
          target_id           = string
          target_type         = string
        }
      ))
      source = set(object(
        {
          is_valid            = bool
          target_display_name = string
          target_id           = string
          target_type         = string
        }
      ))
      sources_excluded = bool
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
resource "nsxt_firewall_section" "this" {
  description   = var.description
  display_name  = var.display_name
  insert_before = var.insert_before
  section_type  = var.section_type
  stateful      = var.stateful

  dynamic "applied_to" {
    for_each = var.applied_to
    content {
      target_id   = applied_to.value["target_id"]
      target_type = applied_to.value["target_type"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {
      action                = rule.value["action"]
      description           = rule.value["description"]
      destinations_excluded = rule.value["destinations_excluded"]
      direction             = rule.value["direction"]
      disabled              = rule.value["disabled"]
      display_name          = rule.value["display_name"]
      ip_protocol           = rule.value["ip_protocol"]
      logged                = rule.value["logged"]
      notes                 = rule.value["notes"]
      rule_tag              = rule.value["rule_tag"]
      sources_excluded      = rule.value["sources_excluded"]

      dynamic "applied_to" {
        for_each = rule.value.applied_to
        content {
          target_id   = applied_to.value["target_id"]
          target_type = applied_to.value["target_type"]
        }
      }

      dynamic "destination" {
        for_each = rule.value.destination
        content {
          target_id   = destination.value["target_id"]
          target_type = destination.value["target_type"]
        }
      }

      dynamic "service" {
        for_each = rule.value.service
        content {
          target_id   = service.value["target_id"]
          target_type = service.value["target_type"]
        }
      }

      dynamic "source" {
        for_each = rule.value.source
        content {
          target_id   = source.value["target_id"]
          target_type = source.value["target_type"]
        }
      }

    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_firewall_section.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_firewall_section.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = nsxt_firewall_section.this.is_default
}

output "revision" {
  description = "returns a number"
  value       = nsxt_firewall_section.this.revision
}

output "this" {
  value = nsxt_firewall_section.this
}
```

[top](#index)