# fortios_wanopt_contentdeliverynetworkrule

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wanopt_contentdeliverynetworkrule" {
  source = "./modules/fortios/r/fortios_wanopt_contentdeliverynetworkrule"

  # category - (optional) is a type of string
  category = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # request_cache_control - (optional) is a type of string
  request_cache_control = null
  # response_cache_control - (optional) is a type of string
  response_cache_control = null
  # response_expires - (optional) is a type of string
  response_expires = null
  # status - (optional) is a type of string
  status = null
  # text_response_vcache - (optional) is a type of string
  text_response_vcache = null
  # updateserver - (optional) is a type of string
  updateserver = null

  host_domain_name_suffix = [{
    name = null
  }]

  rules = [{
    content_id = [{
      end_direction   = null
      end_skip        = null
      end_str         = null
      range_str       = null
      start_direction = null
      start_skip      = null
      start_str       = null
      target          = null
    }]
    match_entries = [{
      id = null
      pattern = [{
        string = null
      }]
      target = null
    }]
    match_mode = null
    name       = null
    skip_entries = [{
      id = null
      pattern = [{
        string = null
      }]
      target = null
    }]
    skip_rule_mode = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_cache_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_cache_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_expires" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "text_response_vcache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "updateserver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_domain_name_suffix" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      content_id = list(object(
        {
          end_direction   = string
          end_skip        = number
          end_str         = string
          range_str       = string
          start_direction = string
          start_skip      = number
          start_str       = string
          target          = string
        }
      ))
      match_entries = list(object(
        {
          id = number
          pattern = list(object(
            {
              string = string
            }
          ))
          target = string
        }
      ))
      match_mode = string
      name       = string
      skip_entries = list(object(
        {
          id = number
          pattern = list(object(
            {
              string = string
            }
          ))
          target = string
        }
      ))
      skip_rule_mode = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_contentdeliverynetworkrule" "this" {
  # category - (optional) is a type of string
  category = var.category
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # request_cache_control - (optional) is a type of string
  request_cache_control = var.request_cache_control
  # response_cache_control - (optional) is a type of string
  response_cache_control = var.response_cache_control
  # response_expires - (optional) is a type of string
  response_expires = var.response_expires
  # status - (optional) is a type of string
  status = var.status
  # text_response_vcache - (optional) is a type of string
  text_response_vcache = var.text_response_vcache
  # updateserver - (optional) is a type of string
  updateserver = var.updateserver

  dynamic "host_domain_name_suffix" {
    for_each = var.host_domain_name_suffix
    content {
      # name - (optional) is a type of string
      name = host_domain_name_suffix.value["name"]
    }
  }

  dynamic "rules" {
    for_each = var.rules
    content {
      # match_mode - (optional) is a type of string
      match_mode = rules.value["match_mode"]
      # name - (optional) is a type of string
      name = rules.value["name"]
      # skip_rule_mode - (optional) is a type of string
      skip_rule_mode = rules.value["skip_rule_mode"]

      dynamic "content_id" {
        for_each = rules.value.content_id
        content {
          # end_direction - (optional) is a type of string
          end_direction = content_id.value["end_direction"]
          # end_skip - (optional) is a type of number
          end_skip = content_id.value["end_skip"]
          # end_str - (optional) is a type of string
          end_str = content_id.value["end_str"]
          # range_str - (optional) is a type of string
          range_str = content_id.value["range_str"]
          # start_direction - (optional) is a type of string
          start_direction = content_id.value["start_direction"]
          # start_skip - (optional) is a type of number
          start_skip = content_id.value["start_skip"]
          # start_str - (optional) is a type of string
          start_str = content_id.value["start_str"]
          # target - (optional) is a type of string
          target = content_id.value["target"]
        }
      }

      dynamic "match_entries" {
        for_each = rules.value.match_entries
        content {
          # id - (optional) is a type of number
          id = match_entries.value["id"]
          # target - (optional) is a type of string
          target = match_entries.value["target"]

          dynamic "pattern" {
            for_each = match_entries.value.pattern
            content {
              # string - (optional) is a type of string
              string = pattern.value["string"]
            }
          }

        }
      }

      dynamic "skip_entries" {
        for_each = rules.value.skip_entries
        content {
          # id - (optional) is a type of number
          id = skip_entries.value["id"]
          # target - (optional) is a type of string
          target = skip_entries.value["target"]

          dynamic "pattern" {
            for_each = skip_entries.value.pattern
            content {
              # string - (optional) is a type of string
              string = pattern.value["string"]
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
output "category" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.category
}

output "id" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.name
}

output "request_cache_control" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.request_cache_control
}

output "response_cache_control" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.response_cache_control
}

output "response_expires" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.response_expires
}

output "status" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.status
}

output "text_response_vcache" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.text_response_vcache
}

output "updateserver" {
  description = "returns a string"
  value       = fortios_wanopt_contentdeliverynetworkrule.this.updateserver
}

output "this" {
  value = fortios_wanopt_contentdeliverynetworkrule.this
}
```

[top](#index)