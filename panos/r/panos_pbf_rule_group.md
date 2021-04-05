# panos_pbf_rule_group

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
module "panos_pbf_rule_group" {
  source = "./modules/panos/r/panos_pbf_rule_group"

  # position_keyword - (optional) is a type of string
  position_keyword = null
  # position_reference - (optional) is a type of string
  position_reference = null
  # vsys - (optional) is a type of string
  vsys = null

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
    name     = null
    schedule = null
    source = [{
      addresses  = []
      interfaces = []
      negate     = null
      users      = []
      zones      = []
    }]
    tags = []
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "vsys" {
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
      name     = string
      schedule = string
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
      uuid = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_pbf_rule_group" "this" {
  position_keyword   = var.position_keyword
  position_reference = var.position_reference
  vsys               = var.vsys

  dynamic "rule" {
    for_each = var.rule
    content {
      active_active_device_binding = rule.value["active_active_device_binding"]
      description                  = rule.value["description"]
      disabled                     = rule.value["disabled"]
      name                         = rule.value["name"]
      schedule                     = rule.value["schedule"]
      tags                         = rule.value["tags"]
      uuid                         = rule.value["uuid"]

      dynamic "destination" {
        for_each = rule.value.destination
        content {
          addresses    = destination.value["addresses"]
          applications = destination.value["applications"]
          negate       = destination.value["negate"]
          services     = destination.value["services"]
        }
      }

      dynamic "forwarding" {
        for_each = rule.value.forwarding
        content {
          action           = forwarding.value["action"]
          egress_interface = forwarding.value["egress_interface"]
          next_hop_type    = forwarding.value["next_hop_type"]
          next_hop_value   = forwarding.value["next_hop_value"]
          vsys             = forwarding.value["vsys"]

          dynamic "monitor" {
            for_each = forwarding.value.monitor
            content {
              disable_if_unreachable = monitor.value["disable_if_unreachable"]
              ip_address             = monitor.value["ip_address"]
              profile                = monitor.value["profile"]
            }
          }

          dynamic "symmetric_return" {
            for_each = forwarding.value.symmetric_return
            content {
              addresses = symmetric_return.value["addresses"]
              enable    = symmetric_return.value["enable"]
            }
          }

        }
      }

      dynamic "source" {
        for_each = rule.value.source
        content {
          addresses  = source.value["addresses"]
          interfaces = source.value["interfaces"]
          negate     = source.value["negate"]
          users      = source.value["users"]
          zones      = source.value["zones"]
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
  value       = panos_pbf_rule_group.this.id
}

output "this" {
  value = panos_pbf_rule_group.this
}
```

[top](#index)