# panos_nat_rule_group

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
module "panos_nat_rule_group" {
  source = "./modules/panos/r/panos_nat_rule_group"

  # position_keyword - (optional) is a type of string
  position_keyword = null
  # position_reference - (optional) is a type of string
  position_reference = null
  # vsys - (optional) is a type of string
  vsys = null

  rule = [{
    description = null
    disabled    = null
    name        = null
    original_packet = [{
      destination_addresses = []
      destination_interface = null
      destination_zone      = null
      service               = null
      source_addresses      = []
      source_zones          = []
    }]
    tags = []
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
      description = string
      disabled    = bool
      name        = string
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
resource "panos_nat_rule_group" "this" {
  # position_keyword - (optional) is a type of string
  position_keyword = var.position_keyword
  # position_reference - (optional) is a type of string
  position_reference = var.position_reference
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "rule" {
    for_each = var.rule
    content {
      # description - (optional) is a type of string
      description = rule.value["description"]
      # disabled - (optional) is a type of bool
      disabled = rule.value["disabled"]
      # name - (required) is a type of string
      name = rule.value["name"]
      # tags - (optional) is a type of list of string
      tags = rule.value["tags"]
      # type - (optional) is a type of string
      type = rule.value["type"]

      dynamic "original_packet" {
        for_each = rule.value.original_packet
        content {
          # destination_addresses - (required) is a type of set of string
          destination_addresses = original_packet.value["destination_addresses"]
          # destination_interface - (optional) is a type of string
          destination_interface = original_packet.value["destination_interface"]
          # destination_zone - (required) is a type of string
          destination_zone = original_packet.value["destination_zone"]
          # service - (optional) is a type of string
          service = original_packet.value["service"]
          # source_addresses - (required) is a type of set of string
          source_addresses = original_packet.value["source_addresses"]
          # source_zones - (required) is a type of set of string
          source_zones = original_packet.value["source_zones"]
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
                  # address - (required) is a type of string
                  address = dynamic.value["address"]
                  # distribution - (optional) is a type of string
                  distribution = dynamic.value["distribution"]
                  # port - (optional) is a type of number
                  port = dynamic.value["port"]
                }
              }

              dynamic "dynamic_translation" {
                for_each = destination.value.dynamic_translation
                content {
                  # address - (required) is a type of string
                  address = dynamic_translation.value["address"]
                  # distribution - (optional) is a type of string
                  distribution = dynamic_translation.value["distribution"]
                  # port - (optional) is a type of number
                  port = dynamic_translation.value["port"]
                }
              }

              dynamic "static" {
                for_each = destination.value.static
                content {
                  # address - (required) is a type of string
                  address = static.value["address"]
                  # port - (optional) is a type of number
                  port = static.value["port"]
                }
              }

              dynamic "static_translation" {
                for_each = destination.value.static_translation
                content {
                  # address - (required) is a type of string
                  address = static_translation.value["address"]
                  # port - (optional) is a type of number
                  port = static_translation.value["port"]
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
                  # translated_addresses - (required) is a type of set of string
                  translated_addresses = dynamic_ip.value["translated_addresses"]

                  dynamic "fallback" {
                    for_each = dynamic_ip.value.fallback
                    content {

                      dynamic "interface_address" {
                        for_each = fallback.value.interface_address
                        content {
                          # interface - (required) is a type of string
                          interface = interface_address.value["interface"]
                          # ip_address - (optional) is a type of string
                          ip_address = interface_address.value["ip_address"]
                          # type - (optional) is a type of string
                          type = interface_address.value["type"]
                        }
                      }

                      dynamic "translated_address" {
                        for_each = fallback.value.translated_address
                        content {
                          # translated_addresses - (optional) is a type of set of string
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
                      # interface - (required) is a type of string
                      interface = interface_address.value["interface"]
                      # ip_address - (optional) is a type of string
                      ip_address = interface_address.value["ip_address"]
                    }
                  }

                  dynamic "translated_address" {
                    for_each = dynamic_ip_and_port.value.translated_address
                    content {
                      # translated_addresses - (optional) is a type of set of string
                      translated_addresses = translated_address.value["translated_addresses"]
                    }
                  }

                }
              }

              dynamic "static_ip" {
                for_each = source.value.static_ip
                content {
                  # bi_directional - (optional) is a type of bool
                  bi_directional = static_ip.value["bi_directional"]
                  # translated_address - (required) is a type of string
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
  value       = panos_nat_rule_group.this.id
}

output "this" {
  value = panos_nat_rule_group.this
}
```

[top](#index)