# avi_wafpolicypsmgroup

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_wafpolicypsmgroup" {
  source = "./modules/avi/r/avi_wafpolicypsmgroup"

  # description - (optional) is a type of string
  description = null
  # enable - (optional) is a type of bool
  enable = null
  # hit_action - (optional) is a type of string
  hit_action = null
  # is_learning_group - (optional) is a type of bool
  is_learning_group = null
  # miss_action - (optional) is a type of string
  miss_action = null
  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  locations = [{
    description = null
    index       = null
    match = [{
      host = [{
        match_case     = null
        match_criteria = null
        value          = []
      }]
      methods = [{
        match_criteria = null
        methods        = []
      }]
      path = [{
        match_case        = null
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
    }]
    name = null
    rules = [{
      description = null
      enable      = null
      index       = null
      match_case  = null
      match_elements = [{
        excluded    = null
        index       = null
        name        = null
        sub_element = null
      }]
      match_value_max_length = null
      match_value_pattern    = null
      mode                   = null
      name                   = null
      paranoia_level         = null
      rule_id                = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hit_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_learning_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "miss_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "locations" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      index       = number
      match = set(object(
        {
          host = set(object(
            {
              match_case     = string
              match_criteria = string
              value          = list(string)
            }
          ))
          methods = set(object(
            {
              match_criteria = string
              methods        = list(string)
            }
          ))
          path = set(object(
            {
              match_case        = string
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
        }
      ))
      name = string
      rules = list(object(
        {
          description = string
          enable      = bool
          index       = number
          match_case  = string
          match_elements = list(object(
            {
              excluded    = bool
              index       = number
              name        = string
              sub_element = string
            }
          ))
          match_value_max_length = number
          match_value_pattern    = string
          mode                   = string
          name                   = string
          paranoia_level         = string
          rule_id                = string
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
resource "avi_wafpolicypsmgroup" "this" {
  description       = var.description
  enable            = var.enable
  hit_action        = var.hit_action
  is_learning_group = var.is_learning_group
  miss_action       = var.miss_action
  name              = var.name
  tenant_ref        = var.tenant_ref
  uuid              = var.uuid

  dynamic "locations" {
    for_each = var.locations
    content {
      description = locations.value["description"]
      index       = locations.value["index"]
      name        = locations.value["name"]

      dynamic "match" {
        for_each = locations.value.match
        content {

          dynamic "host" {
            for_each = match.value.host
            content {
              match_case     = host.value["match_case"]
              match_criteria = host.value["match_criteria"]
              value          = host.value["value"]
            }
          }

          dynamic "methods" {
            for_each = match.value.methods
            content {
              match_criteria = methods.value["match_criteria"]
              methods        = methods.value["methods"]
            }
          }

          dynamic "path" {
            for_each = match.value.path
            content {
              match_case        = path.value["match_case"]
              match_criteria    = path.value["match_criteria"]
              match_str         = path.value["match_str"]
              string_group_refs = path.value["string_group_refs"]
            }
          }

        }
      }

      dynamic "rules" {
        for_each = locations.value.rules
        content {
          description            = rules.value["description"]
          enable                 = rules.value["enable"]
          index                  = rules.value["index"]
          match_case             = rules.value["match_case"]
          match_value_max_length = rules.value["match_value_max_length"]
          match_value_pattern    = rules.value["match_value_pattern"]
          mode                   = rules.value["mode"]
          name                   = rules.value["name"]
          paranoia_level         = rules.value["paranoia_level"]
          rule_id                = rules.value["rule_id"]

          dynamic "match_elements" {
            for_each = rules.value.match_elements
            content {
              excluded    = match_elements.value["excluded"]
              index       = match_elements.value["index"]
              name        = match_elements.value["name"]
              sub_element = match_elements.value["sub_element"]
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
output "description" {
  description = "returns a string"
  value       = avi_wafpolicypsmgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_wafpolicypsmgroup.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_wafpolicypsmgroup.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_wafpolicypsmgroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_wafpolicypsmgroup.this.uuid
}

output "this" {
  value = avi_wafpolicypsmgroup.this
}
```

[top](#index)