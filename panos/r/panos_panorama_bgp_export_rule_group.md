# panos_panorama_bgp_export_rule_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_bgp_export_rule_group" {
  source = "./modules/panos/r/panos_panorama_bgp_export_rule_group"

  # position_keyword - (optional) is a type of string
  position_keyword = null
  # position_reference - (optional) is a type of string
  position_reference = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # virtual_router - (required) is a type of string
  virtual_router = null

  rule = [{
    action                   = null
    as_path_limit            = null
    as_path_type             = null
    as_path_value            = null
    community_type           = null
    community_value          = null
    enable                   = null
    extended_community_type  = null
    extended_community_value = null
    local_preference         = null
    match_address_prefix = [{
      exact  = null
      prefix = null
    }]
    match_as_path_regex            = null
    match_community_regex          = null
    match_extended_community_regex = null
    match_from_peers               = []
    match_med                      = null
    match_next_hops                = []
    match_route_table              = null
    med                            = null
    name                           = null
    next_hop                       = null
    origin                         = null
    used_by                        = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "position_keyword" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "position_reference" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      action                   = string
      as_path_limit            = number
      as_path_type             = string
      as_path_value            = string
      community_type           = string
      community_value          = string
      enable                   = bool
      extended_community_type  = string
      extended_community_value = string
      local_preference         = string
      match_address_prefix = set(object(
        {
          exact  = bool
          prefix = string
        }
      ))
      match_as_path_regex            = string
      match_community_regex          = string
      match_extended_community_regex = string
      match_from_peers               = list(string)
      match_med                      = string
      match_next_hops                = list(string)
      match_route_table              = string
      med                            = string
      name                           = string
      next_hop                       = string
      origin                         = string
      used_by                        = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_bgp_export_rule_group" "this" {
  position_keyword   = var.position_keyword
  position_reference = var.position_reference
  template           = var.template
  template_stack     = var.template_stack
  virtual_router     = var.virtual_router

  dynamic "rule" {
    for_each = var.rule
    content {
      action                         = rule.value["action"]
      as_path_limit                  = rule.value["as_path_limit"]
      as_path_type                   = rule.value["as_path_type"]
      as_path_value                  = rule.value["as_path_value"]
      community_type                 = rule.value["community_type"]
      community_value                = rule.value["community_value"]
      enable                         = rule.value["enable"]
      extended_community_type        = rule.value["extended_community_type"]
      extended_community_value       = rule.value["extended_community_value"]
      local_preference               = rule.value["local_preference"]
      match_as_path_regex            = rule.value["match_as_path_regex"]
      match_community_regex          = rule.value["match_community_regex"]
      match_extended_community_regex = rule.value["match_extended_community_regex"]
      match_from_peers               = rule.value["match_from_peers"]
      match_med                      = rule.value["match_med"]
      match_next_hops                = rule.value["match_next_hops"]
      match_route_table              = rule.value["match_route_table"]
      med                            = rule.value["med"]
      name                           = rule.value["name"]
      next_hop                       = rule.value["next_hop"]
      origin                         = rule.value["origin"]
      used_by                        = rule.value["used_by"]

      dynamic "match_address_prefix" {
        for_each = rule.value.match_address_prefix
        content {
          exact  = match_address_prefix.value["exact"]
          prefix = match_address_prefix.value["prefix"]
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
  value       = panos_panorama_bgp_export_rule_group.this.id
}

output "this" {
  value = panos_panorama_bgp_export_rule_group.this
}
```

[top](#index)