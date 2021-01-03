# panos_panorama_nat_rule_group

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
module "panos_panorama_nat_rule_group" {
  source = "./modules/panos/r/panos_panorama_nat_rule_group"

  # device_group - (optional) is a type of string
  device_group = null
  # position_keyword - (optional) is a type of string
  position_keyword = null
  # position_reference - (optional) is a type of string
  position_reference = null
  # rulebase - (optional) is a type of string
  rulebase = null

  rule = [{
    description   = null
    disabled      = null
    name          = null
    negate_target = null
    original_packet = [{
      destination_addresses = []
      destination_interface = null
      destination_zone      = null
      service               = null
      source_addresses      = []
      source_zones          = []
    }]
    tags = []
    target = [{
      serial    = null
      vsys_list = []
    }]
    translated_packet = [{
      destination = [{
        dynamic = [{
          address      = null
          distribution = null
          port         = null
        }]
        dynamic_translation = [{
          address      = null
          distribution = null
          port         = null
        }]
        static = [{
          address = null
          port    = null
        }]
        static_translation = [{
          address = null
          port    = null
        }]
      }]
      source = [{
        dynamic_ip = [{
          fallback = [{
            interface_address = [{
              interface  = null
              ip_address = null
              type       = null
            }]
            translated_address = [{
              translated_addresses = []
            }]
          }]
          translated_addresses = []
        }]
        dynamic_ip_and_port = [{
          interface_address = [{
            interface  = null
            ip_address = null
          }]
          translated_address = [{
            translated_addresses = []
          }]
        }]
        static_ip = [{
          bi_directional     = null
          translated_address = null
        }]
      }]
    }]
    type = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "position_reference" {
  description = "(optional)"
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
      description   = string
      disabled      = bool
      name          = string
      negate_target = bool
      original_packet = list(object(
        {
          destination_addresses = set(string)
          destination_interface = string
          destination_zone      = string
          service               = string
          source_addresses      = set(string)
          source_zones          = set(string)
        }
      ))
      tags = list(string)
      target = set(object(
        {
          serial    = string
          vsys_list = set(string)
        }
      ))
      translated_packet = list(object(
        {
          destination = list(object(
            {
              dynamic = list(object(
                {
                  address      = string
                  distribution = string
                  port         = number
                }
              ))
              dynamic_translation = list(object(
                {
                  address      = string
                  distribution = string
                  port         = number
                }
              ))
              static = list(object(
                {
                  address = string
                  port    = number
                }
              ))
              static_translation = list(object(
                {
                  address = string
                  port    = number
                }
              ))
            }
          ))
          source = list(object(
            {
              dynamic_ip = list(object(
                {
                  fallback = list(object(
                    {
                      interface_address = list(object(
                        {
                          interface  = string
                          ip_address = string
                          type       = string
                        }
                      ))
                      translated_address = list(object(
                        {
                          translated_addresses = set(string)
                        }
                      ))
                    }
                  ))
                  translated_addresses = set(string)
                }
              ))
              dynamic_ip_and_port = list(object(
                {
                  interface_address = list(object(
                    {
                      interface  = string
                      ip_address = string
                    }
                  ))
                  translated_address = list(object(
                    {
                      translated_addresses = set(string)
                    }
                  ))
                }
              ))
              static_ip = list(object(
                {
                  bi_directional     = bool
                  translated_address = string
                }
              ))
            }
          ))
        }
      ))
      type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_nat_rule_group" "this" {
  device_group       = var.device_group
  position_keyword   = var.position_keyword
  position_reference = var.position_reference
  rulebase           = var.rulebase

  dynamic "rule" {
    for_each = var.rule
    content {
      description   = rule.value["description"]
      disabled      = rule.value["disabled"]
      name          = rule.value["name"]
      negate_target = rule.value["negate_target"]
      tags          = rule.value["tags"]
      type          = rule.value["type"]

      dynamic "original_packet" {
        for_each = rule.value.original_packet
        content {
          destination_addresses = original_packet.value["destination_addresses"]
          destination_interface = original_packet.value["destination_interface"]
          destination_zone      = original_packet.value["destination_zone"]
          service               = original_packet.value["service"]
          source_addresses      = original_packet.value["source_addresses"]
          source_zones          = original_packet.value["source_zones"]
        }
      }

      dynamic "target" {
        for_each = rule.value.target
        content {
          serial    = target.value["serial"]
          vsys_list = target.value["vsys_list"]
        }
      }

      dynamic "translated_packet" {
        for_each = rule.value.translated_packet
        content {

          dynamic "destination" {
            for_each = translated_packet.value.destination
            content {

              dynamic "dynamic" {
                for_each = destination.value.dynamic
                content {
                  address      = dynamic.value["address"]
                  distribution = dynamic.value["distribution"]
                  port         = dynamic.value["port"]
                }
              }

              dynamic "dynamic_translation" {
                for_each = destination.value.dynamic_translation
                content {
                  address      = dynamic_translation.value["address"]
                  distribution = dynamic_translation.value["distribution"]
                  port         = dynamic_translation.value["port"]
                }
              }

              dynamic "static" {
                for_each = destination.value.static
                content {
                  address = static.value["address"]
                  port    = static.value["port"]
                }
              }

              dynamic "static_translation" {
                for_each = destination.value.static_translation
                content {
                  address = static_translation.value["address"]
                  port    = static_translation.value["port"]
                }
              }

            }
          }

          dynamic "source" {
            for_each = translated_packet.value.source
            content {

              dynamic "dynamic_ip" {
                for_each = source.value.dynamic_ip
                content {
                  translated_addresses = dynamic_ip.value["translated_addresses"]

                  dynamic "fallback" {
                    for_each = dynamic_ip.value.fallback
                    content {

                      dynamic "interface_address" {
                        for_each = fallback.value.interface_address
                        content {
                          interface  = interface_address.value["interface"]
                          ip_address = interface_address.value["ip_address"]
                          type       = interface_address.value["type"]
                        }
                      }

                      dynamic "translated_address" {
                        for_each = fallback.value.translated_address
                        content {
                          translated_addresses = translated_address.value["translated_addresses"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "dynamic_ip_and_port" {
                for_each = source.value.dynamic_ip_and_port
                content {

                  dynamic "interface_address" {
                    for_each = dynamic_ip_and_port.value.interface_address
                    content {
                      interface  = interface_address.value["interface"]
                      ip_address = interface_address.value["ip_address"]
                    }
                  }

                  dynamic "translated_address" {
                    for_each = dynamic_ip_and_port.value.translated_address
                    content {
                      translated_addresses = translated_address.value["translated_addresses"]
                    }
                  }

                }
              }

              dynamic "static_ip" {
                for_each = source.value.static_ip
                content {
                  bi_directional     = static_ip.value["bi_directional"]
                  translated_address = static_ip.value["translated_address"]
                }
              }

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
output "id" {
  description = "returns a string"
  value       = panos_panorama_nat_rule_group.this.id
}

output "this" {
  value = panos_panorama_nat_rule_group.this
}
```

[top](#index)