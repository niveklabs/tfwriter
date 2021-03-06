# panos_panorama_pbf_rule_group

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
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_pbf_rule_group" {
  source = "./modules/panos/r/panos_panorama_pbf_rule_group"

  # device_group - (optional) is a type of string
  device_group = null
  # position_keyword - (optional) is a type of string
  position_keyword = null
  # position_reference - (optional) is a type of string
  position_reference = null
  # rulebase - (optional) is a type of string
  rulebase = null

  rule = [{
    active_active_device_binding = null
    description                  = null
    destination = [{
      addresses    = []
      applications = []
      negate       = null
      services     = []
    }]
    disabled = null
    forwarding = [{
      action           = null
      egress_interface = null
      monitor = [{
        disable_if_unreachable = null
        ip_address             = null
        profile                = null
      }]
      next_hop_type  = null
      next_hop_value = null
      symmetric_return = [{
        addresses = []
        enable    = null
      }]
      vsys = null
    }]
    name          = null
    negate_target = null
    schedule      = null
    source = [{
      addresses  = []
      interfaces = []
      negate     = null
      users      = []
      zones      = []
    }]
    tags = []
    target = [{
      serial    = null
      vsys_list = []
    }]
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "position_keyword" {
  description = "(optional) - The position keyword for this group of rules"
  type        = string
  default     = null
}

variable "position_reference" {
  description = "(optional) - The position reference for this group of rules"
  type        = string
  default     = null
}

variable "rulebase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      active_active_device_binding = string
      description                  = string
      destination = list(object(
        {
          addresses    = set(string)
          applications = set(string)
          negate       = bool
          services     = set(string)
        }
      ))
      disabled = bool
      forwarding = list(object(
        {
          action           = string
          egress_interface = string
          monitor = list(object(
            {
              disable_if_unreachable = bool
              ip_address             = string
              profile                = string
            }
          ))
          next_hop_type  = string
          next_hop_value = string
          symmetric_return = list(object(
            {
              addresses = list(string)
              enable    = bool
            }
          ))
          vsys = string
        }
      ))
      name          = string
      negate_target = bool
      schedule      = string
      source = list(object(
        {
          addresses  = set(string)
          interfaces = set(string)
          negate     = bool
          users      = set(string)
          zones      = set(string)
        }
      ))
      tags = list(string)
      target = set(object(
        {
          serial    = string
          vsys_list = set(string)
        }
      ))
      uuid = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_pbf_rule_group" "this" {
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # position_keyword - (optional) is a type of string
  position_keyword = var.position_keyword
  # position_reference - (optional) is a type of string
  position_reference = var.position_reference
  # rulebase - (optional) is a type of string
  rulebase = var.rulebase

  dynamic "rule" {
    for_each = var.rule
    content {
      # active_active_device_binding - (optional) is a type of string
      active_active_device_binding = rule.value["active_active_device_binding"]
      # description - (optional) is a type of string
      description = rule.value["description"]
      # disabled - (optional) is a type of bool
      disabled = rule.value["disabled"]
      # name - (required) is a type of string
      name = rule.value["name"]
      # negate_target - (optional) is a type of bool
      negate_target = rule.value["negate_target"]
      # schedule - (optional) is a type of string
      schedule = rule.value["schedule"]
      # tags - (optional) is a type of list of string
      tags = rule.value["tags"]
      # uuid - (optional) is a type of string
      uuid = rule.value["uuid"]

      dynamic "destination" {
        for_each = rule.value.destination
        content {
          # addresses - (required) is a type of set of string
          addresses = destination.value["addresses"]
          # applications - (required) is a type of set of string
          applications = destination.value["applications"]
          # negate - (optional) is a type of bool
          negate = destination.value["negate"]
          # services - (required) is a type of set of string
          services = destination.value["services"]
        }
      }

      dynamic "forwarding" {
        for_each = rule.value.forwarding
        content {
          # action - (optional) is a type of string
          action = forwarding.value["action"]
          # egress_interface - (optional) is a type of string
          egress_interface = forwarding.value["egress_interface"]
          # next_hop_type - (optional) is a type of string
          next_hop_type = forwarding.value["next_hop_type"]
          # next_hop_value - (optional) is a type of string
          next_hop_value = forwarding.value["next_hop_value"]
          # vsys - (optional) is a type of string
          vsys = forwarding.value["vsys"]

          dynamic "monitor" {
            for_each = forwarding.value.monitor
            content {
              # disable_if_unreachable - (optional) is a type of bool
              disable_if_unreachable = monitor.value["disable_if_unreachable"]
              # ip_address - (optional) is a type of string
              ip_address = monitor.value["ip_address"]
              # profile - (optional) is a type of string
              profile = monitor.value["profile"]
            }
          }

          dynamic "symmetric_return" {
            for_each = forwarding.value.symmetric_return
            content {
              # addresses - (optional) is a type of list of string
              addresses = symmetric_return.value["addresses"]
              # enable - (optional) is a type of bool
              enable = symmetric_return.value["enable"]
            }
          }

        }
      }

      dynamic "source" {
        for_each = rule.value.source
        content {
          # addresses - (required) is a type of set of string
          addresses = source.value["addresses"]
          # interfaces - (optional) is a type of set of string
          interfaces = source.value["interfaces"]
          # negate - (optional) is a type of bool
          negate = source.value["negate"]
          # users - (required) is a type of set of string
          users = source.value["users"]
          # zones - (optional) is a type of set of string
          zones = source.value["zones"]
        }
      }

      dynamic "target" {
        for_each = rule.value.target
        content {
          # serial - (required) is a type of string
          serial = target.value["serial"]
          # vsys_list - (optional) is a type of set of string
          vsys_list = target.value["vsys_list"]
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
  value       = panos_panorama_pbf_rule_group.this.id
}

output "this" {
  value = panos_panorama_pbf_rule_group.this
}
```

[top](#index)